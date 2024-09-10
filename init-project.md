# Инициализация проекта

- Создаем git -репозиторий
- Делаем clone
- Создаем шаблон react-приложения `pnpm create vite@latest`
- Устанавливаем зависимости `pnpm install`

# Добавление prettier

- Устанаваливаем пакет в DEV зависимости `pnpm install -D prettier`
- Создаем файл в корне проекта `.prettierrc.json`

### Конфиг prettier

```json5
{
  "printWidth": 80, //длина строки
  "tabWidth": 2, // ширина таба
  "semi": true, // точка с запятой в конце строки
  "singleQuote": false, // "
  "trailingComma": "all", // висящая запятая
  "endOfLine": "lf" // тип конца строки
}
```

# Git-ветки и удаленный репозиторий

- Создание ветки и переход на неё
```
git checkout -B "nameBranch"
```

- Создаем ветку в удаленном репозитории
```
git push -u origin update/title
```


# Добавление alias(для путей)

- Устанавливаем пакет для сборщика проектов `pnpm i vite-tsconfig-paths`
- Добавляем плагин в vite.config.ts сборщика `plugins: [react(), tsConfigPaths()]`
- Конфигурируем `tsconfig.app.json`
```json5
{
  "compilerOptions": {
    /* other params */

    /* typescript paths */
    "baseUrl": "src",
    "paths": {
      "@app/*": ["*"]
    }
  }
}
```

Использование

```ts
import { Component } from '@app/common';
```

Или

```ts
import { Component } from 'app/common';
```
