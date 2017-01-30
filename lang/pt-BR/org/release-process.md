* * *

id: release_process guide: yarn_organization layout: guide

* * *

## Para lançar uma nova versão do Yarn [](#toc-to-release-a-new-version-of-yarn){#toc-to-release-a-new-version-of-yarn.toc}

  1. Certifique-se de que os testes da branch master estão passando no [Circle](https://circleci.com/gh/yarnpkg/yarn) e [Travis](https://travis-ci.com/yarnpkg/yarn/builds)
  2. Certifique-se de que sua cópia local do Yarn está atualizada, então execute `./scripts/release-branch.sh`. Isto vai criar a branch `0.xx-stable` e o CircleCI vai criar, automaticamente, uma nova versão de lançamento no GitHub a partir dessa branch
  3. Uma vez que a versão de lançamento no GitHub foi criada, anexe o arquivo `.msi` do [build do AppVeyor daquela branch](https://ci.appveyor.com/project/kittens/yarn) para a versão de lançamento do GitHub. Note que isto **não** está automatizado como nós vamos precisar para a assinar os instaladores no Authenticode no futuro (que será feito externamente para o AppVeyor)
  4. Garanta que todos os artefatos estão anexados na release (`.tar.gz`, `.deb`, `.rpm` e `.msi`). **Não continue** antes de garantir isto
  5. Incremente `latest_version` no arquivo [_config.yml no website](https://github.com/yarnpkg/website/blob/master/_config.yml#L9). Isto atualiza a URL de download (`/latest.tar.gz` etc) para apontar para a nova versão. Isto vai, eventualmente, ser automatizado ([#187](https://github.com/yarnpkg/website/issues/187))
  6. Repositórios do Debian e CentOS deveriam ser automaticamente atualizados com a última versão dentro de 5 minutos (fique de olho [nos commits](https://github.com/yarnpkg/releases/commits/gh-pages))

<!-- [TODO: Instructions for updating Chocolatey should go here - Currrently Daniel does that manually] -->

## Para corrigir um bug em uma versão do Yarn [](#toc-to-patch-existing-version-of-yarn){#toc-to-patch-existing-version-of-yarn.toc}

- Troque para a branch lançada `git checkout 0.x-stable`, exemplo: 0.7-stable
- Faça cherry-pick das correções a partir da branch master
- Crie a tag para a nova versão de lançamento `npm version patch`. Isto irá criar um commit com o package.json alterado e a tag `v0.xx.1` para aquele commit
- Faça push no origin `git push origin 0.x-stable --follow-tags`

## Processo manual antigo [](#toc-old-manual-process){#toc-old-manual-process.toc}

Esta é a forma que as versões eram lançadas antigamente, para referência (se caso algum passo automatizado quebrar). Gerar uma nova versão de lançamento era um processo de dois passos - A maior parte das coisas é feita no Linux, e algumas coisas são específicas para Windows (como o instalador do Windows), que é gerado no Windows.

**No Linux:**

  1. `./scripts/release-branch.sh`
  2. Gere os pacotes do Debian e RPM: `./scripts/build-deb.sh`
  3. Anexe os arquivos `.deb` e `.rpm` do diretório `artifacts` para a versão de lançamento do GitHub

**No Windows:**

  1. Faça o build do Yarn normalmente (`yarn install && yarn run build`)
  2. `powershell .\scripts\build-dist.ps1`
  3. Gerando o instalador do Windows: `yarn run build-win-installer` 
    - A FAZER: Adicionar assinatura Authenticode para o instalador ([#619](https://github.com/yarnpkg/yarn/issues/619))
  4. Gere o pacote para o Chocolately `yarn run build-chocolatey`
  5. Anexe o arquivo `.msi` resultante do diretório `artifacts` para a versão de lançamento do GitHub
  6. [Suba o pacote do Chocolatey](https://chocolatey.org/packages/upload) (no futuro nós devemos automatizar isto). 
    - Nota: Só faça isto quando o MSI for anexado à versão de lançamento do GitHub, pois o Chocolatey puxa o MSI pelo link de download
    - Outra nota: O pacote do Chocolatey vai quebrar se você modificar o MSI depois de fazer o upload do pacote, pois ele contém uma hash para o MSI. Certifique-se de sempre atualizar ambos ao mesmo tempo!