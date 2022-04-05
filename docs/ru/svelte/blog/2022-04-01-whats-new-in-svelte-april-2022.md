---
title: "Что нового в Svelte: Апрель 2022"
description: "Прощай перебор маршрутов, привет валидатор параметров!"
author: Daniel Sandoval
authorURL: https://desandoval.net
---

В этом месяце мы почувствовали изменение в том, как SvelteKit обрабатывает свойства страницы. Последний вариант использования, требующий перебора маршрутов и проверки свойств параметров, был заменен более конкретным решением.

Подробнее об этом и о том, что еще нового в Svelte, мы погружаемся в...

## Что нового в SvelteKit
- Сопоставление параметров позволяет вам проверять, соответствует ли параметр URL-адреса перед отображением страницы - заменяя необходимость в обходных маршрутах для этой цели ([Документы](https://ru.kit.svelte.dev/docs#marshruty-rasshirennaya-marshrutizacziya-sopostavlenie), [#4334](https://github.com/sveltejs/kit/pull/4334))
- Явные перенаправления теперь можно обрабатывать непосредственно с эндпоинтов ([#4260](https://github.com/sveltejs/kit/pull/4260))
- `svelte-kit sync` ([#4182](https://github.com/sveltejs/kit/pull/4182)), TypeScript 4.6 ([#4190](https://github.com/sveltejs/kit/pull/4190)) и Vite 2.9 - добавлена ​​неблокирующая оптимизация зависимостей и экспериментальные исходные карты CSS в режиме разработки, а также ряд исправлений ошибок, внесенных командой SvelteKit ([#4468](https://githubюcom/sveltejs/kit/pull/4468))


**Новые параметры конфигурации**
- `outDir` исправляет проблемы с путями в монорепозиториях и других ситуациях, когда желаемый выходной каталог находится за пределами каталога проекта ([Docs](https://ru.kit.svelte.dev/docs#konfiguracziya-outdir), [#4176](https://github.com/sveltejs/kit/pull/4176))
- `endpointExtensions` предотвращает обработку файлов, отличных от файлов .js и .ts, в качестве эндпоинтов, если только вы не укажете endpointExtensions ([Docs](https://ru.kit.svelte.dev/docs#konfiguracziya-endpointextensions), [#4197](https://github.com/sveltejs/kit/pull/4197))
- `prerender.default` позволяет выполнять предварительную отрисовку каждой страницы без необходимости писать `export const prerender = true` в каждом файле страницы ([Docs](https://ru.kit.svelte.dev/docs#konfiguracziya-prerender), [#4192](https://github.com/sveltejs/kit/pull/4192))


**Breaking Changes**
- Перебор маршрутов был удален. Советы по миграции см. в PR ([#4330](https://github.com/sveltejs/kit/pull/4330))
- `tabindex="-1"` добавляется к `<body>` только во время навигации ([#4140](https://github.com/sveltejs/kit/pull/4140) и [#4184](https://github.com/sveltejs/kit/pull/4184))
- Адаптеры теперь требуются для предоставления функции getClientAddress ([#4289](https://github.com/sveltejs/kit/pull/4289))
- `InputProps` и `OutputProps` теперь можно вводить отдельно в сгенерированном `Load` ([#4305](https://github.com/sveltejs/kit/pull/4305))
- Символ `\$` больше не разрешен в динамических параметрах ([#4334](https://github.com/sveltejs/kit/pull/4334))
- Пакет `svelte-kit` помечен как экспериментальный, поэтому изменения в нем после Kit 1.0 не будут считаться нарушением ([#4164](https://github.com/sveltejs/kit/pull/4164))


## Новое в экосистеме Svelte
- Svelte: множество новых типов для пользователей плагинов TypeScript и Svelte, включая директивы `style:` и действия Svelte (**3.46.4** и **3.46.5**)
- Языковые инструменты: файлы проекта Svelte теперь можно импортировать/находить по ссылкам без их импорта в файл TS ([105.13.0](https://github.com/sveltejs/language-tools/releases/tag/extensions-105.13.0))
- Языковые инструменты: свертывание регионов теперь поддерживается в html с помощью `<!--#region-->`/`<!--#endregion-->` ([105.13.0](https://github.com/sveltejs/language-tools/releases/tag/extensions-105.13.0))

---

## Крутые примеры сообщества

**Приложения и сайты, созданные с помощью Svelte**
- [Launcher](https://launchчer.team/) — это средство запуска приложений с открытым исходным кодом на базе SvelteKit, Prisma и Tailwind.
- [Paaster](https://paaster.io/) — это безопасный по умолчанию сквозной зашифрованный pastebin, созданный с помощью Svelte, Vite, Typescript, Python, Starlette, rclone и Docker.
- [Simple AF Video Converter](https://github.com/berlyozzy/Simple-AF-Video-Converter) — это оболочка Electron вокруг ffmpeg.wasm, упрощающая конвертирование видео разных форматов.
- [Streamchaser](https://github.com/streamchaser/streamchaser) стремится упростить поиск фильмов, сериалов и документальных фильмов с помощью централизованной платформы развлекательных технологий.
- [Svelte Color Picker](https://github.com/V-Py/svelte-material-color-picker) — простая палитра цветов, созданная с помощью Svelte.
- [ConcertMash](https://github.com/mcmxcdev/ConcertMash) — это небольшой веб-сайт, который взаимодействует с API Spotify и создает новые списки воспроизведения на основе предстоящих концертов, которые вы посещаете.
- [Modulus](https://modulus.vision/) — это аналитический центр Design+Code, созданный с целью развития дизайна и технологий.
- [Multiply](https://www.multiply.us/) — интегрированное агентство по связям с общественностью и социальным сетям, развивающееся со скоростью культуры.
- [yia!](https://www.yia.co.nz/) — конкурс молодых новаторов в Новой Зеландии.
- [Write to Russia](https://www.writetorussia.org/index) — это платформа для написания электронных писем сообщества для общения с общедоступными адресами электронной почты `.ru`
- [Markdown Playground](https://github.com/Petros-K/markdown-playground) — это онлайн-площадка, предназначенная для ваших экспериментов с Markdown.
- [RatherMisty](https://rathermisty.com/) — простое погодное приложение с данными о погоде от Open-Meteo.
- [Minecraft Profile Pic (MCPFP)](https://github.com/MauritsWilke/mcpfp) — это сайт для удобного создания изображений профиля Minecraft.
- [WebGL Fluid Simulation](https://github.com/jpaquim/svelte-webgl-fluid-simulation) — это настраиваемая симуляция жидкости, созданная с помощью Svelte и WebGL.
- [This @NobelPeaceOslo exhibition](https://twitter.com/perbyhring/status/1504754949791621120) была построена с использованием печатной графики, проекционной графики движения, анимации частиц и генеративного звукового дизайна.

Не терпится внести свой вклад в современный веб-сайт SvelteKit? 
[Помогите создать сайт Svelte Society](https://github.com/svelte-society/sveltesociety.dev/issues)!


**Образовательные ресурсы**

_Посещать_
- [Svelte Summit: Spring](https://www.sveltesummit.com/) состоится 30 апреля 2022 года! Присоединяйтесь к нам на 5-й виртуальной конференции Svelte на [YouTube](https://www.sveltesummit.com/) и Discord 🍾

_Читать_
- [Svelte(Kit) TypeScript Showcase + общие советы по TypeScript](https://github.com/ivanhofer/sveltekit-typescript-showcase) от Хофера Ивана
- [Локальные константы в Svelte с тегом @const](https://geoffrich.net/posts/local-constants/) Джеффа Рича
- [Шаблоны проектирования для создания переиспользуемых компонентов Svelte](https://render.com/blog/svelte-design-patterns) Эрика Лю.
- [Svelte лучше, чем React](https://labs.hamy.xyz/posts/svelte-is-better-than-react/) Гамильтона Грина.
- [Буквальное создание визуализаций с помощью Svelte и D3](https://www.connorrothschild.com/post/svelte-and-d3) Коннора Ротшильда.
- [Координация нескольких элементов с отложенными переходами Svelte](https://imfeld.dev/writing/svelte_deferred_transitions) Дэниела Имфельда
- [Анимация при прокрутке с помощью Svelte Inview — Little Bits](https://dev.to/maciekgrzybek/animate-on-scroll-with-svelte-inview-266f) от Maciek Grzybek
- [Отложенная загрузка Firebase с помощью SvelteKit](https://www.captaincodeman.com/lazy-loading-firebase-with-sveltekit) и [Компоненты HeadlessUI с помощью Svelte](https://www.captaincodeman.com/headlessui-components-with-svelte) от Captain Codeman
- [Тестирование доступности SvelteKit: автоматизированные тесты CI A11y](https://rodneylab.com/sveltekit-accessibility-testing/) от Rodney Lab.
- [Начало работы с KitQL и GraphCMS](https://scottspence.com/posts/getting-started-with-kitql-and-graphcms) Скотта Спенса.
- [React ⇆ Svelte Cheatsheet](https://dev.to/joshnuss/react-to-svelte-cheatsheet-1a2a) перечисляет сходства и различия между двумя библиотеками - Джошуа Нуссбаум

_Смотреть_
- [Стройная феерия | Асинхронный](https://www.youtube.com/watch?v=mT4CLVHgtSg) от pngwn
- [6 пакетов Svelte, которые вы должны знать](https://www.youtube.com/watch?v=y5SrUKcX_Co) и [Основное преобразование React To Svelte](https://www.youtube.com/watch?v=DiSuwLlhOxs). ) от LevelUpTuts
- [Конечная точка страницы/тени в SvelteKit](https://www.youtube.com/watch?v=j-9D5UDyVOM) от WebJeda
- [Custom Svelte Store: Higher Order Store](https://www.youtube.com/watch?v=p1aPfVyZ1IY) от lihautan
- [SvelteKit для начинающих (плейлист)](https://www.youtube.com/watch?v=bLBHecY4-ak&list=PLA9WiRZ-IS_zXZZyW4qfj0akvOAtk6MFS) от Joy of Code - следуйте [руководству по блогу](https://joyofcode.xyz/sveltekit-for-beginners)
- [Полная авторизация SvelteKit 🔐 с Firebase и Magic Links! 🪄](https://www.youtube.com/watch?v=MAHE4iQgh5Q) Джонни Магрипписа
- [Аутентификация Firebase в SvelteKit! Приложение Full Stack](https://www.youtube.com/watch?v=N6Y3hqhZvNI) Райана Бодди


**Библиотеки, инструменты и компоненты**
- [SvelTable](https://sveltable.io/) — многофункциональный компонент таблицы данных, созданный с помощью Svelte.
- [svelte-cyberComp](https://github.com/Cybersteam00/svelte-cyberComp) — мощная и легкая библиотека компонентов, написанная на Svelte и Typescript
- [Flowbite Svelte](https://github.com/shinokada/flowbite-svelte) — неофициальная библиотека компонентов Flowbite для Svelte.
- [Svelte-Tide-Project](https://github.com/jbertovic/svelte-tide-project) — начальный шаблон для интерфейсных приложений Svelte с внутренним сервером Rust Tide.
- [Fetch Inject](https://github.com/vhscom/fetch-inject#sveltekit) реализует метод оптимизации производительности для управления асинхронными зависимостями JavaScript — теперь с поддержкой Svelte.
- [svelte-utterances](https://github.com/shinokada/svelte-utterances) — легкий виджет комментариев, созданный на основе проблем GitHub.
- [Liquivelte](https://github.com/malipetek/liquivelte-vscode) позволяет создать тему Shopify с компонентами, подобными Svelte.
- [@storyblok/svelte](https://github.com/storyblok/storyblok-svelte) — Svelte SDK, необходимый для взаимодействия с Storyblok API и обеспечения возможности визуального редактирования в реальном времени.
- [@svelte-on-solana/wallet-adapter](https://github.com/svelte-on-solana/wallet-adapter) — это модульный адаптер кошелька TypeScript и компоненты пользовательского интерфейса для приложений Solana/Anchor, использующих SvelteJS в качестве фреймворка.
- [svelte-lookat](https://www.npmjs.com/package/svelte-lookat) создает div, который заставляет все его дочерние элементы следовать за курсором мыши или лицом пользователя при использовании мобильного телефона.

Присоединяйтесь к нам на [Reddit](https://www.reddit.com/r/sveltejs/) или [Discord](https://discord.com/invite/yy75DKs), чтобы продолжить общение.

Увидимся в следующем месяце!
