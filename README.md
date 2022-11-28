# modal-dialog

Сделать на Vue визуальный компонент - модальный диалог. Содержимое диалога поступает в умолчательный слот. У компонента должен быть метод show(), который запускает диалог и возвращает Promise, разрешающийся при выходе из диалога (когда пользователь нажимает ОК или другую кнопку), с результатом выбора пользователя в диалоге. Кнопки диалога должны настраиваться (должно быть удобно).
Плюсом будет возможность валидации, возможность управления скроллингом.

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
