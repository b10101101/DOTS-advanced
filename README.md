# DOTS³ - Dynamic Orbit Tracing Simulator

![GitHub stars](https://img.shields.io/github/stars/b10101101/DOTS-advanced?style=social)
![GitHub forks](https://img.shields.io/github/forks/b10101101/DOTS-advanced?style=social)

<p align="center">
  <a href="#english-version"><strong>English</strong></a> | <a href="#russian-version"><strong>Русский</strong></a>
</p>

<a id="english-version"></a>

DOTS³ is a powerful, browser-based design tool for creating and analyzing **intersecting circle puzzles**. It allows for the visual exploration of complex geometric patterns that form the basis for new puzzle designs. As the third generation of the ["dots"](http://codercontest.com/dots.html) utility by Tomas Rokicki, it expands on original concepts with a modern UI and multiple analysis engines.

This project is aimed at the community of puzzle designers and enthusiasts.

**[Try it live!](https://b10101101.github.io/DOTS-advanced/DOTS___v1.8.7_standalone.html)**

<img width="599" height="384" alt="Fig 01" src="https://github.com/user-attachments/assets/5213f83a-5ab8-4277-9797-1cb6ef4bca8c" />

---

## Key Features

- **Up to 4 Circles:** Create intricate patterns with up to four fully configurable circles.
- **Multiple Render Engines:**
  - **Fast Chaos:** A high-performance generative algorithm for rapid pattern discovery.
  - **Slicer:** A deterministic engine that precisely calculates all intersections, arcs, and contours.
  - **Layer Mixer:** A static image generator that creates woven patterns by mixing layers.
  - **Macro Rotator:** A procedural simulator that executes user-defined rotation sequences step-by-step.
- **Interactive UI:** Full control via mouse and keyboard, including draggable markers, sliders, and precise input dialogs.
- **Advanced State Management:** Undo/Redo, session saving, and import/export of states as `.json` files and via clipboard.
- **Flexible Anchor System:** Anchor one circle's center to another, creating hierarchical links. Moving a parent circle also moves its children, allowing for complex kinematic chains.

## Core Hotkeys

### State and File Management

| Key / Combination    | Action                                                        |
| :------------------- | :------------------------------------------------------------ |
| `Ctrl` + `Z`         | Undo the last action.                                         |
| `Ctrl` + `Y`         | Redo the last undone action.                                  |
| `Ctrl + Shift` + `S` | Save the current state to history manually.                   |
| `Ctrl` + `C`         | Copy state to clipboard.                                      |
| `Ctrl` + `V`         | Paste state from clipboard.                                   |
| `Ctrl` + `S`         | Export the current state to a `.json` file.                   |
| `Ctrl` + `O`         | Import the current state from a `.json` file.                 |
| `S`                  | Take a screenshot (`.png`) and save the state file (`.json`). |

### View and Navigation

| Key / Combination  | Action                                             |
| :----------------- | :------------------------------------------------- |
| `←`, `↑`, `→`, `↓` | Pan the canvas. Holding down accelerates movement. |
| `Mouse Wheel`      | Zoom In/Out relative to the cursor.                |
| `0`                | Center the view (reset canvas offset).             |
| `[`                | Zoom Out.                                          |
| `]`                | Zoom In.                                           |

### Circle Management

| Key / Combination  | Action                                                                |
| :----------------- | :-------------------------------------------------------------------- |
| `1`, `2`, `3`, `4` | Toggle circles A, B, C, D respectively.                               |
| `Alt` + `1`...`4`  | Select the corresponding circle for editing (opens the slider panel). |
| `Q`                | Show/hide the slider panel for the selected circle.                   |
| `A`                | Show/hide the information panels.                                     |

### Display Modes and Styles

| Key / Combination | Action                                                                 |
| :---------------- | :--------------------------------------------------------------------- |
| `J`               | Cycle through **Slicer** styles (Off → Borders → Fill → Fill+Numbers). |
| `K`               | Toggle **Layer Mixer** mode (layer overlay simulation).                |
| `D`               | Cycle through **Fast Chaos** point rendering modes.                    |
| `W`               | Switch between color and grayscale mode for **Fast Chaos**.            |
| `P`               | Generate a new color palette (color mode only).                        |
| `Z`               | Show/hide the main **Fast Chaos** canvas.                              |
| `X`               | Show/hide the **Slicer** canvas with markers.                          |
| `C`               | Show/hide the **Layer Mixer** canvas.                                  |
| `V`               | Show/hide the **Macro Rotator** canvas.                                |

### Miscellaneous

| Key / Combination | Action                                                                       |
| :---------------- | :--------------------------------------------------------------------------- |
| `H` or `F1`       | Show/hide the full help window.                                              |
| `~`               | Show/hide the browser console output window.                                 |
| `Esc`             | Close the current active window (sliders, help, settings, coordinate input). |

### Center Marker (●)

| Key / Combination         | Action                                                                       |
| :------------------------ | :--------------------------------------------------------------------------- |
| `🖱️ [LMB]` + **Drag**     | Free movement of the circle's center.                                        |
| `🖱️ [RMB]` + **Drag**     | Moving the center of the circle "with sticking" to the axes.                 |
| `🖱️` + `←`, `↑`, `→`, `↓` | Change coordinates in increments of **0.001**.                               |
| `🖱️` + `Shift`            | Move only horizontally (lock Y-axis).                                        |
| `🖱️` + `Ctrl`             | Move only vertically (lock X-axis).                                          |
| `🖱️` + `Alt`              | Change polar angle (φ) while keeping radius (ρ). Rotation around the anchor. |
| `🖱️` + `Shift + Ctrl`     | Change radius (ρ) while keeping polar angle (φ). Movement along the angle.   |
| `🖱️` + `Shift + Alt`      | Change angle with rotation of linked circles.                                |

### Radius Marker (■)

| Key / Combination         | Action                                                           |
| :------------------------ | :--------------------------------------------------------------- |
| `🖱️ [LMB]` + **Drag**     | Change the circle's radius.                                      |
| `🖱️ [RMB]` + **Drag**     | Changing the radius with snapping to the radii of other circles. |
| `🖱️` + `←`, `↑`, `→`, `↓` | Change the radius in increments of **0.001**.                    |
| `Ctrl` + **Mouse Wheel**  | Change the `Spin` parameter (number of rotation sectors).        |
| `Shift` + **Mouse Wheel** | Change the `Spin Angle` parameter (total rotation angle).        |

### Parameter Input

#### Parameter Input Window

| Key / Combination               | Action                                                     |
| :------------------------------ | :--------------------------------------------------------- |
| `Ctrl` + `🖱️` on the info panel | Opens a window for precise coordinate and parameter input. |

#### Slider Panel

| Key / Combination                    | Action                                           |
| :----------------------------------- | :----------------------------------------------- |
| Slider + **Mouse Wheel** + `Shift`   | Change the parameter in increments of **1**.     |
| Slider + **Mouse Wheel**             | Change the parameter in increments of **0.1**.   |
| Slider + **Mouse Wheel** + `Ctrl`    | Change the parameter in increments of **0.01**.  |
| Slider + **Keys** `←`, `↑`, `→`, `↓` | Change the parameter in increments of **0.001**. |

## Acknowledgements

- **The original "dots" utility by Tomas Rokicki:** [twistypuzzles.com forum post](https://twistypuzzles.com/forum/viewtopic.php?p=419246#p419246)
- **Added features from Evgeniy Grigoriev:** [GeraniumsPot on GitHub](https://github.com/grigorusha/GeraniumsPot/blob/main/Applet/dots4.html)

## License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.

## Support

If you find this project useful and would like to support its development, please consider making a donation. Your support is greatly appreciated!

- **Bitcoin (BTC):** `bc1qxjt4h7fevyfhmysplzps8sw5sf00uf3zvf3hes`
- **Toncoin (TON):** `UQDQPcMCmmfiaIzKf5ID6LM9zHgL1xn8hWSftPOShxl3sJTy`

---

<a id="russian-version"></a>

# DOTS³ - Dynamic Orbit Tracing Simulator

DOTS³ — это мощный браузерный инструмент для проектирования и анализа **головоломок с пересекающимися кругами**. Он позволяет визуально исследовать сложные геометрические узоры, которые лежат в основе дизайна новых головоломок. Являясь третьим поколением утилиты ["dots"](http://codercontest.com/dots.html) Tomas Rokicki, он расширяет исходные концепции за счет современного интерфейса и нескольких движков для анализа.

Этот проект нацелен на сообщество дизайнеров головоломок и энтузиастов.

**[Попробовать онлайн!](https://b10101101.github.io/DOTS-advanced/DOTS___v1.8.7_standalone.html)**

<img width="599" height="384" alt="Fig 01" src="https://github.com/user-attachments/assets/5213f83a-5ab8-4277-9797-1cb6ef4bca8c" />

---

## Ключевые возможности

- **До 4 окружностей:** Создавайте сложные узоры, используя до четырех полностью настраиваемых окружностей.
- **Несколько движков рендеринга:**
  - **Fast Chaos:** Высокопроизводительный генеративный алгоритм для быстрого поиска узоров.
  - **Slicer:** Детерминированный движок, который точно рассчитывает все пересечения, дуги и контуры.
  - **Layer Mixer:** Генератор статичных изображений, создающий "плетеные" узоры путем смешивания слоев.
  - **Macro Rotator:** Процедурный симулятор, пошагово выполняющий заданные пользователем последовательности вращений.
- **Интерактивный интерфейс:** Полный контроль с помощью мыши и клавиатуры, включая перетаскиваемые маркеры, слайдеры и диалоги точного ввода.
- **Продвинутое управление состоянием:** Отмена/Повтор действий (Undo/Redo), сохранение сессий, импорт/экспорт состояний в формате `.json` и через буфер обмена.
- **Гибкая система якорей:** Привязывайте центр одной окружности к другой, создавая иерархические связи. Перемещение родительской окружности двигает все дочерние, что позволяет создавать сложные кинематические цепочки.

## Основные горячие клавиши

### Управление состоянием и файлами

| Клавиша / Комбинация | Действие                                                        |
| :------------------- | :-------------------------------------------------------------- |
| `Ctrl` + `Z`         | Отменить последнее действие (Undo).                             |
| `Ctrl` + `Y`         | Повторить отмененное действие (Redo).                           |
| `Ctrl + Shift` + `S` | Сохранить текущее состояние в историю вручную.                  |
| `Ctrl` + `C`         | Копировать состояние в буфер обмена.                            |
| `Ctrl` + `V`         | Вставить состояние из буфера обмена.                            |
| `Ctrl` + `S`         | Экспортировать текущее состояние в `.json` файл.                |
| `Ctrl` + `O`         | Импортировать текущее состояние из `.json` файла.               |
| `S`                  | Сделать скриншот (`.png`) и сохранить файл состояния (`.json`). |

### Управление видом и навигация

| Клавиша / Комбинация | Действие                                                             |
| :------------------- | :------------------------------------------------------------------- |
| `←`, `↑`, `→`, `↓`   | Перемещение (панорамирование) холста. Удерживание ускоряет движение. |
| `Колесико мыши`      | Масштабирование (Zoom In/Out) относительно курсора.                  |
| `0`                  | Центрировать вид (сбросить смещение холста).                         |
| `[`                  | Уменьшить масштаб (Zoom Out).                                        |
| `]`                  | Увеличить масштаб (Zoom In).                                         |

### Управление окружностями

| Клавиша / Комбинация | Действие                                                                      |
| :------------------- | :---------------------------------------------------------------------------- |
| `1`, `2`, `3`, `4`   | Включить/выключить окружности A, B, C, D соответственно.                      |
| `Alt` + `1`...`4`    | Выбрать соответствующий круг для редактирования (открывает панель слайдеров). |
| `Q`                  | Показать/скрыть панель слайдеров для выбранного круга.                        |
| `A`                  | Показать/скрыть информационные панели.                                        |

### Режимы и стили отображения

| Клавиша / Комбинация | Действие                                                                                |
| :------------------- | :-------------------------------------------------------------------------------------- |
| `J`                  | Циклическое переключение стилей **Slicer** (Выкл → Границы → Заливка → Заливка+Номера). |
| `K`                  | Включить/выключить режим **Layer Mixer** (симуляция наложения слоев).                   |
| `D`                  | Циклическое переключение режимов отрисовки точек **Fast Chaos**.                        |
| `W`                  | Переключение между цветным и монохромным (Grayscale) режимом для **Fast Chaos**.        |
| `P`                  | Сгенерировать новую цветовую палитру (только в цветном режиме).                         |
| `Z`                  | Показать/скрыть основной холст **Fast Chaos**.                                          |
| `X`                  | Показать/скрыть холст **Slicer**.                                                       |
| `C`                  | Показать/скрыть холст **Layer Mixer**.                                                  |
| `V`                  | Показать/скрыть холст **Macro Rotator**.                                                |

### Прочее

| Клавиша / Комбинация | Действие                                                                      |
| :------------------- | :---------------------------------------------------------------------------- |
| `H` или `F1`         | Показать/скрыть окно полной справки.                                          |
| `~`                  | Показать/скрыть окно вывода консоли браузера.                                 |
| `Esc`                | Закрыть текущее активное окно (слайдеры, справка, настройки, ввод координат). |

### Маркер центра (●)

| Клавиша / Комбинация            | Действие                                                                        |
| :------------------------------ | :------------------------------------------------------------------------------ |
| `🖱️ [ЛКМ]` + **Перетаскивание** | Свободное перемещение центра окружности.                                        |
| `🖱️ [ПКМ]` + **Перетаскивание** | Перемещение центра окружности "с прилипанием" к осям.                           |
| `🖱️` + `←`, `↑`, `→`, `↓`       | Изменение координат с шагом **0.001**.                                          |
| `🖱️` + `Shift`                  | Перемещение только по горизонтали (блокировка оси Y).                           |
| `🖱️` + `Ctrl`                   | Перемещение только по вертикали (блокировка оси X).                             |
| `🖱️` + `Alt`                    | Изменение полярного угла (φ) при сохранении радиуса (ρ). Вращение вокруг якоря. |
| `🖱️` + `Shift + Ctrl`           | Изменение радиуса (ρ) при сохранении полярного угла (φ). Движение по углу.      |
| `🖱️` + `Shift + Alt`            | Изменение угла с вращением связанных окружностей.                               |

### Маркер радиуса (■)

| Клавиша / Комбинация            | Действие                                                         |
| :------------------------------ | :--------------------------------------------------------------- |
| `🖱️ [ЛКМ]` + **Перетаскивание** | Изменение радиуса окружности.                                    |
| `🖱️ [ПКМ]` + **Перетаскивание** | Изменение радиуса "с прилипанием" к радиусам других окружностей. |
| `🖱️` + `←`, `↑`, `→`, `↓`       | Изменение радиуса с шагом **0.001**.                             |
| `Ctrl` + **Колесико мыши**      | Изменение параметра `Spin` (количество секторов вращения).       |
| `Shift` + **Колесико мыши**     | Изменение параметра `Spin Angle` (общий угол вращения).          |

### Ввод параметров

#### Окно ввода параметров

| Клавиша / Комбинация         | Действие                                            |
| :--------------------------- | :-------------------------------------------------- |
| `Ctrl` + `🖱️` на инфо-панели | Открытие окна точного ввода координат и параметров. |

#### Панель слайдеров

| Клавиша / Комбинация                     | Действие                               |
| :--------------------------------------- | :------------------------------------- |
| Слайдер + **Колесико мыши** + `Shift`    | Изменение параметра с шагом **1**.     |
| Слайдер + **Колесико мыши**              | Изменение параметра с шагом **0.1**.   |
| Слайдер + **Колесико мыши** + `Ctrl`     | Изменение параметра с шагом **0.01**.  |
| Слайдер + **Клавиши** `←`, `↑`, `→`, `↓` | Изменение параметра с шагом **0.001**. |

## Благодарности

- **Изначальная утилита "dots" (Томас Рокицки):** [Пост на форуме twistypuzzles.com](https://twistypuzzles.com/forum/viewtopic.php?p=419246#p419246)
- **Дальнейшее развитие (Евгений Григорьев):** [GeraniumsPot на GitHub](https://github.com/grigorusha/GeraniumsPot/blob/main/Applet/dots4.html)

## Лицензия

Проект распространяется под лицензией MIT. Подробности в файле LICENSE.md.

## Поддержка проекта

Если вы находите этот проект полезным и хотели бы поддержать его развитие, пожалуйста, рассмотрите возможность сделать пожертвование. Ваша поддержка очень ценится!

- **Bitcoin (BTC):** `bc1qxjt4h7fevyfhmysplzps8sw5sf00uf3zvf3hes`
- **Toncoin (TON):** `UQDQPcMCmmfiaIzKf5ID6LM9zHgL1xn8hWSftPOShxl3sJTy`
