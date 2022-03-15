# Roteiro Git flow

Comandos para aula sobre **Gitflow**

```
mkdir nome_pasta
cd nome_pasta
git init
```
    git flow init

![gitflow-init.png](https://i.postimg.cc/9QwM2yDF/gitflow-init.png)](https://postimg.cc/QFssk9gR)

## Feature

Para criar uma nova feature (ou funcionalidade) em nossa aplicação podemos criar uma nova branch da seguinte forma:

    git flow feature start nova-feature
[![gitflow-new-feature.png](https://i.postimg.cc/NGWG45N3/gitflow-new-feature.png)](https://postimg.cc/K4Dycvhf)

Temos agora a nova feature e podemos trabalhar as novas funcionalidade.
[![gitflow-make-newfeature.png](https://i.postimg.cc/gkYS1KB8/gitflow-make-newfeature.png)](https://postimg.cc/Z0Mxd6m5)

### Finalizando a feature
Terminadas as novas funcionalidades e feito os testes, podemos rodar o comando para fechar essa branch e criar o merge para develop.

    git flow feature finish new-feature
[![gitflow-finish-newfeature.png](https://i.postimg.cc/26yjHvND/gitflow-finish-newfeature.png)](https://postimg.cc/LYdM5JsC)
Com isso algumas coisas aconteceram:

 - Merge da feature para a branch Develop;
 - Branch da nova-feature foi deletada;
 - Feito o checkout para Develop;
## Release
Para iniciar uma nova release de nossa aplicação rodamos o comando:

    git flow release start release-teste
  [![gitflow-new-release.png](https://i.postimg.cc/DzZdcj0y/gitflow-new-release.png)](https://postimg.cc/gxCZzK3f)

É criada uma nova branch e somos redirecionados para ela.
E aí podemos finalizar nossa release:

    git flow release finish release-teste 1.0.0
[![gitflow-finish-release.png](https://i.postimg.cc/3NcHdbk4/gitflow-finish-release.png)](https://postimg.cc/D4LNN6dn)
Aparece Vi (ou o editor configurado) para que se crie uma mensagem sobre o release.
[![gitflow-release-finished.png](https://i.postimg.cc/NFrdkNNr/gitflow-release-finished.png)](https://postimg.cc/64tV9hx9)
Com isso algumas ações foram realizadas:

 - Merge de release com Master E Develop;
 - criação da tag release-teste na master;
 - deletada branch de release;
 - checkout para Develop.
## Hotfix
Vamos supor que foi achado um bug em produção e queremos corrigir imediatamente com uma correção de emergência.

    git flow hotfix start hotfix-bug01
[![gitflow-hotfix-start.png](https://i.postimg.cc/v8WqTK6p/gitflow-hotfix-start.png)](https://postimg.cc/6TpL1Yc0)
Foi criada nova branch e é feito o checkout para ela. 
Vamos simular uma correção no nosso arquivo JS.
[![gitflow-hotfix-fix.png](https://i.postimg.cc/cHG7NsT6/gitflow-hotfix-fix.png)](https://postimg.cc/GBzTFnW1)
Feita a correção podemos finalizar o hotfix com o comando:

    git flow hotfix finish hotfix-bug01 -n
[![gitflow-hotfix-finish.png](https://i.postimg.cc/TPM5Ktb4/gitflow-hotfix-finish.png)](https://postimg.cc/DS6wDdBr)
Usamos a flag -n para evitar o erro de dizer que não tem tag definida (não é o escopo aqui);


