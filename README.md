# Callback (Коллбек) - Тавзеҳ ва Методҳо

## Муқаддима
Callback як функсияест, ки ҳамчун аргумент ба функсияи дигар дода шуда, баъдтар (ҳангоми рух додани рӯйдод ё мувофиқи зарурат) иҷро мешавад. Ин метод дар забонҳои барномасозии C++, JavaScript, Python ва бисёр дигар забонҳо васеъ истифода мешавад.

Callback-ҳо барои:
- Идоракунии рӯйдодҳо (event-driven programming)
- Имплементи механизмҳои асинхронӣ
- Инкапсулятсияи мантиқ дар функсияҳои дигар
истифода мешаванд.

## Намуна дар JavaScript
Дар JavaScript, Callback-ҳо одатан барои кор бо рӯйдодҳо ва механизмҳои асинхронӣ, мисли `setTimeout`, `fetch` ё дигар функсияҳо истифода мешаванд.

### Намуна бо Synchronous Callback
```javascript
function greeting(name) {
    console.log(`Салом, ${name}!`);
}

function processUserInput(callback) {
    const name = "Алишер";
    callback(name);
}

processUserInput(greeting);
```

### Намуна бо Asynchronous Callback
```javascript
function fetchData(callback) {
    setTimeout(() => {
        const data = { id: 1, name: "Тавзеҳот" };
        callback(data);
    }, 2000);
}

fetchData((data) => {
    console.log("Маълумот дастрас шуд:", data);
});
```

### Намуна бо Promises (Беҳбудбахши Callback)
```javascript
function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            const data = { id: 1, name: "Тавзеҳот" };
            resolve(data);
        }, 2000);
    });
}

fetchData().then((data) => {
    console.log("Маълумот дастрас шуд:", data);
});
```

### Намуна бо async/await
```javascript
function fetchData() {
    return new Promise((resolve) => {
        setTimeout(() => {
            const data = { id: 1, name: "Тавзеҳот" };
            resolve(data);
        }, 2000);
    });
}

async function getData() {
    const data = await fetchData();
    console.log("Маълумот дастрас шуд:", data);
}

getData();
```

## Намудҳои Callback
1. **Synchronous Callback**: Callback фавран иҷро мешавад ва натиҷаи онро фавран мебинем.
2. **Asynchronous Callback**: Callback баъд аз анҷоми рӯйдод ё вазифа иҷро мешавад.

## Бартариҳо
- Имкон медиҳад, ки код бештар модуляр ва созмонёфта бошад.
- Ба осонӣ барои системаҳое, ки бо рӯйдодҳо кор мекунанд, татбиқ мегардад.

## Камбудиҳо
- Дарки кор бо callback метавонад барои шурӯъкунандагон душвор бошад.
- Callback Hell: Ҳангоми зиёд шудани функсияҳои якдигариро даъваткунанда, код душворфаҳм мегардад.

## Қайдҳо
- Барои беҳтар фаҳмидани callback, истифодаи Promises ва async/await тавсия дода мешавад.
- Дар муҳитҳои асинхронӣ, сохтори кодро бо истифода аз функсияҳои нав ба нав оптималӣ созед.

