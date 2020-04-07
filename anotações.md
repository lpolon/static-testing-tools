# ESlint
- Os vídeos e as outras branchs tem exemplos interessnates de configuração do ESLint. Vale Olhar antes de colocar no projeto.
- a extensão de eslint do vscode, apenas dá o highlight dos erros que seriam apontados se rodar o script (npx eslint .)
- ctrl + . = npx eslint . --fix => autofix

- ao invés de configurar cada regra, podemos pegar "configurações recomendadas": é a key extends.

-  rules mantém o use strict, porque o babel já irá cuidar disso pra gente e não precisamos jogar erros.

- para garantir que todos vão rodar o link da mesma forma, há o script npm run lint. Porém, o npm run build irá gerar arquivos de configuração e aplicar o linting na build! Para evitar isso, acrescentamos o arquivo .eslintignore OU, acrescentar no script a flag --ignore-path .gitignore.

# prettier
formatação de erros.

- instalar prettier como dev dependency
- o script é ``npx prettier src.example.js``
- o auto formatting é ``npx prettier src.example.js --write``
- está no package.json como prettier

# evitar conflitos prettier e eslint
- dev-dependency eslint-config-prettier;
- e acrescentar no .eslintrc

# npm run...
o "-- " do format significa que as flags do outro script estão sendo preservadas. Evitando diplicação.

# typescript
- no caso, o babel é o compilador desse exemplo, o tsconfig.json está fazendo apenas o papel de type checking.

- Esse arquivo tem configurações para o babel fazer a transpilação de typescript também.

- Várias configurações adicionais do linter para funcionar e evitar conflitos.

# husky
- o validate script evita qualquer erro de typagem estático.
- Seria muito legal se pudessemos evitar commits com esse tipo de erro =D
- exemplo: ``cat .git/hooks/pre-commit``:
  ele acrescenta o script de validate ao pré-commit na cfg de .huskyrc