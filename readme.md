<!-- ДЗ 43. Пояснити чому є різниця між встановленою та виведеною годиною.
let date = new Date();

console.log('First date', date);

date.setFullYear(2024);
date.setMonth(11);
date.setDate(25);
date.setHours(12); 
date.setMinutes(45);
date.setSeconds(30);

console.log('Second date', date); -->

Різниця виникає тому що Node.js використовує часовий пояс UTC для виведення дати, 
а ми знаходимося в часовому поясі UTF+3 в літній час та UTF+2 в інший час. 
За замовчуванням в терміналі дата виводиться в форматі Date.prototype.toISOString().
Для виведення дати в поточному часовому поясі треба переписати код наступним чином:

let date = new Date();

console.log('First date:', date.toString());

date.setFullYear(2024);
date.setMonth(11);
date.setDate(25);
date.setHours(12); 
date.setMinutes(45);
date.setSeconds(30);

console.log('Second date:', date.toString());
