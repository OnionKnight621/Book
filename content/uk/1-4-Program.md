## 1.4. Алгоритм, программа, синтаксис, мова

Є багато термінів, пов'язаних із програмуванням. Для визначеності нам слід з'ясувати різницю між ними. Краще зосередитися на неформальному розумінні, ніж формальному визначенні. Найстарішим поняттям тут є алгоритм, який ми пам'ятаємо зі шкільного курсу математики. Наприклад, алгоритм Евкліда знаходження найбільшого спільного дільника двох цілих чисел.

> Алгоритм (Algorithm)

Алгоритм це ще не програма, це ідея вирішення задач, описана формально. Так, щоб вона була зрозуміла іншим, вона перевіряється та реалізується. Алгоритм не можна запустити, його можна перетворити на код якоюсь мовою програмування. Алгоритм містить опис операцій і може бути записаний різними способами: формулою, блок-схемою, списком дій, людською мовою. Він завжди обмежений конкретним класом завдань, що він вирішує за кінцевий час. Часто ми можемо спростити та оптимізувати алгоритм, звузивши клас задач. Наприклад, переходячи від обчислення суми цілих і дробових чисел до обчислення суми лише цілих, ми можемо зробити більш ефективну реалізацію. Можна і розширити клас задач для цього прикладу, дозволивши подавати на вхід ще й рядкові подання чисел. Це зробить алгоритм більш універсальним, але менш ефективним. Ми маємо вибирати, що саме ми оптимізуємо. В даному випадку краще розділити алгоритм на два, один перетворюватимє всі числа до одного типу даних, а другий складатиме.

> Приклад реалізації алгоритму НОД (GCD)

На JavaScript алгоритм Евкліда, для знаходження НОД (загальної міри чи найбільшого спільного дільника) можна написати так:

```js
const gcd = (a, b) => {
  if (b === 0) return a;
  return gcd(b, a % b);
};
```

Або навіть коротше, але стане не менш зрозумілим, якщо ви порівняєте два ці варіанти і простежте які конструкції замінені:

```js
const gcd = (a, b) => (b === 0 ? a : gcd(b, a % b));
```

Цей простий алгоритм є рекурсивним, тобто звертається до себе для обчислення наступного кроку і передбачає вихід, коли b доходить до 0. Для алгоритмів ми можемо визначати обчислювальну складність, класифікувати їх за ресурсами процесорного часу та пам'яті, необхідним для вирішення задачі.

> Програма (Program)

У попередньому прикладі ми мали справу з функцією, це частина програми, але щоб вона запрацювала, її потрібно викликати та передати їй дані. Програмний код та дані, об'єднані в одне ціле – це і є програма. Ніклаус Вірт, автор багатьох мов, у тому числі і Pascal, має книгу «Алгоритми + Структури даних = Програми». Її назва схопила дуже важливу істину, яка глибоко відобразилася не тільки у світогляді читачів, а й у назвах курсів у провідних ВНЗ, і навіть на співбесідах, коли випробуваного просять сконцентруватися саме на цих двох речах. За перші 50 років існування індустрії програмного забезпечення виявилося, що структури даних не менш важливі, ніж алгоритми. Більше того, багато відомих програмістів роблять на них основну ставку, наприклад, відома цитата Лінуса Торвальдса: «Погані програмісти турбуються про код. Хороші програмісти турбуються про структури даних та зв'язки між ними». Справа в тому, що вибір структур даних багато в чому визначає те, яким буде алгоритм, обмежує його в рамках обчислювальної складності та семантики завдання, яке програміст розуміє через дані, розкладені в пам'яті, набагато краще, ніж через послідовність операцій.

Ерік Реймонд висловив це так: «Розумні структури даних і тупий код працюють набагато краще, ніж навпаки».

> Код дозволяє порозумітися

Однак той самий Лінус Торвальдс сказав нам «Бовтовня нічого не варта. Покажіть мені код». Це зовсім не суперечить сказаному вище. Я думаю, що він мав на увазі те, що програмний код не допускає двозначності. Це універсальна мова, яка дозволяє програмістам знаходити спільну мову навіть тоді, коли природні мови через свою багатозначність не дозволяють точно зрозуміти один одного, можна зробити це просто поглянувши на код.

> Інженерія (Engineering)

Отримання практичної користі з наявних ресурсів за допомогою науки, техніки, різних методик, організаційної структури, прийомів та знань – це наступний рівень — інженерія.

Я пам'ятаю, що в перші роки вивчення програмування для мене вже було важливо, щоб код використовувався людьми, покращував їхнє життя і жив довго. Олімпіадні завдання здавались мені нецікавими, навчальні завдання надто надуманими, хотілося сконцентруватися на тому, що люди запускатимуть на своїх комп'ютерах щодня: програми баз даних, форми та таблиці, мережеві та комунікаційні програми, програми, що керують апаратурою, працюють з датчиками, та безліч інструментів для програмістів.

Так само, як і в інших інженерних галузях, у програмуванні дуже важлива користь для людини, а не правильність або стрункість концепції. Інженерія покликана використовувати наукові досягнення, а в тих місцях, де наукових знань, що є на сьогодні, недостатньо, інженерія застосовує інтуїцію, інженерну культуру, метод спроб і помилок, застосування неусвідомленого досвіду та досвіду, що має недостатнє наукове осмислення.

У цьому й перевага інженерії та недолік. Ми маємо безліч різних та суперечливих рішень одного завдання, ми не завжди знаємо чому щось не працює, але це ще добре, ми іноді дивуємось, чому щось працює. Такий підхід призводить до накопичення поганих практик у проектах і такого переплетення хороших і поганих практик, що розділити їх дуже складно і часто зусилля витрачаються повторно на вирішені завдання. Ніклаус Вірт сказав «Програми стають повільнішими швидше, ніж "залізо" стає швидше» і ми часто стикаємося з тим, що написати програму наново простіше, ніж виправляти в ній помилки.

> Інженерія програмного забезпечення (Software engineering)

Залучення інженерії до індустрії програмного забезпечення включає архітектуру, дослідження, розробку, тестування, розгортання та підтримку програмного забезпечення.

Індустрія програмного забезпечення перетворилася на потужну галузь промисловості, обросла допоміжними технологічними практиками, які дозволяють зменшити вплив її недоліків, вже наведених вище та зробити кінцевий продукт достатньо надійним, щоб він приносив прибуток, але недостатньо якісним, щоб можна було випускати нові і нові його версії .

«Більшість програм на сьогоднішній день подібні до єгипетських пірамід з мільйона цеглинок одна на одній і без конструктивної цілісності — вони просто побудовані грубою силою і тисячами рабів» // Алан Кей

> Програмування (Programming)

Отже, програмування - це мистецтво та інженерія вирішення завдань за допомогою обчислювальної техніки. Тут важливо відзначити, що обчислювальна техніка дуже сильно впливає на те, як ми програмуємо, диктує те, які парадигми та підходи працюватимуть ефективніше і даватимуть результат, доступний нам за ресурсами, витраченими на програмування та обчислювальними ресурсами, необхідними для виконання створених програм. .

> Кодування (Coding)

Якщо виділити з програмування лише написання вихідного коду програми за допомогою певного синтаксису (мови), стилю та парадигми за готовим ТЗ (технічним завданням), то ми називаємо це кодуванням, хоч слово можна вважати застарілим.

Розробка може бути поділена на проектування та кодування, і це дає більш ефективне застосування сил на довгій дистанції, але часто доводиться починати програмувати без ТЗ і без попереднього проектування. Розроблені таким чином системи називають прототипами, MVP (minimum viable product), пілотними системами або стендами. Їх користь полягає у перевірці гіпотез про корисність для споживача або економічну ефективність їх використання.

Програміст не завжди усвідомлює, що він робить прототип або продукт, і ми отримуємо прототип, зроблений так добротно, як готовий продукт, або готовий продукт, зроблений як тимчасове рішення. Проте є ентузіасти, які люблять свою роботу, і саме на них тримається ця галузь, суперечлива та повна проблем.

«Більшість хороших програмістів роблять свою роботу не тому, що чекають оплати або визнання, а тому, що отримують задоволення від програмування» // Лінус Торвальдс

> Розробник vs програміст

Є прихильники кожної з назв, часто самоназва розробник або програміст пов'язана з особливою професійною гордістю і навіть пихатим ставленням до прихильників іншої назви. Було б добре розділити ці професії приблизно так само, як розділилися професії водія та автомеханіка. Звичайно, автомеханік може говорити, що водії нічого не тямлять у автомобілях, але масово людей возять саме водії. Так само і в ІТ, програміст повинен концентруватися на абстракціях і створенні програмних компонентів, а розробник - на застосуванні готових компонентів до завдання, що вимагає зовсім інших знань і навичок, крім програмування.

Різницю між програмістом і розробником можна показати на прикладі створення інформаційних систем (ІС). У світі є потреба масового виробництва ІС забезпечення потреб промисловості, транспорту, сфери обслуговування, логістики, торгівлі, медицини тощо. Але зараз інформаційні системи (ІС) – це дороге задоволення і для їхньої розробки потрібні висококваліфіковані кадри. ІС, як клас систем, передбачає бази даних, інтерфейси користувача і бізнес-логіку. Майже завжди ІС потребує інтеграції з іншими ІС. Таким чином, для розробки ІС потрібні знання з СУБД (SQL або noSQL), фронтенд (форми, UI/UX), бекенд (сервер додатків) та API. Тому ІС мають велику вартість володіння, а експлуатація пов'язана з високими ризиками. Адже ІС створюють універсальні інженери-програмісти, які пишуть для кожної ІС багато системного коду з нуля. Якщо розділити прикладне та системне програмування на дві різні спеціальності та використовувати високорівневу платформу, яку зробили системні програмісти, ми зможемо перевикористовувати до 80% коду в різних системах. Прикладні програмісти (тобто розробники) зможуть тоді зосередитися лише на завданнях, пов'язаних із специфікою предметної галузі. Це істотно знижує вимоги до прикладних програмістів, а використання принципів вільного програмного забезпечення дозволяє об'єднати зусилля зі створення платформи та виключити ризики, пов'язані з володінням платформою. Open source ліцензії не дають вендорам довільно змінювати свою політику стосовно споживачів та системних інтеграторів, тому що вони не мають блокуючого контролю над платформою і можуть бути замінені конкурентами.

Такий підхід вже застосовувався неодноразово і дозволив зробити доступнішим бухгалтерське та офісне ПЗ, розробку веб-сайтів, навіть комп'ютерні ігри зараз не пишуть з нуля, а використовують платформи, на яких навіть початківці можуть швидко показати вражаючі результати.

Щоб запровадити такий підхід для ІС, нам потрібні нові професії, нова система підготовки кадрів, новий підхід до постановки завдань і навіть замовник таких ІС має думати про них інакше. Існуючий попит має суттєво змінитись, вирости завдяки тому, що тепер спеціалізовані ІС будуть доступні набагато ширшому колу споживачів і перестануть бути розкішшю.

> Складність та простота

Давайте ж прагнути до того, щоб наші програми були простими і для споживача і для нас самих, як людей, які їх багато разів модифікуватимуть і постійно стикатимуться з тими рішеннями, які ми заклали в них під час первинної розробки. А якщо ми обмежені в часі і змушені писати неефективний або малозрозумілий код, то слід планувати його переробку, рефакторинг та оптимізацію до того, як ми забудемо його структуру і у нас вивітряться всі ідеї щодо покращення. Накопичення проблем у коді називається "технічний борг" і він призводить не тільки до того, що програми стають менш гнучкими та зрозумілими, а й до того, що наші молодші колеги, підключаючись до проектів, читають та вбирають не найкращі практики та переймають наш оверинжиніринг. Простота вирішення складних завдань є метою хорошого програміста, приховування складності за програмними абстракціями — це метод досвідченого інженера.

«Я завжди мріяв про те, щоб моїм комп'ютером можна було користуватися так само легко, як телефоном; моя мрія збулася: я вже не можу розібратися, як користуватись моїм телефоном» // Бйорн Страуструп
