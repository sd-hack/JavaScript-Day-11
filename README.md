# JavaScript-Day-11
// =====================
// Task 1: Object
// =====================
let menuItem = {
  name: "Espresso",
  price: 120,
  type: "Drink"
};

console.log(menuItem);           // full object
console.log(menuItem.name);      // dot notation
console.log(menuItem["price"]); // bracket notation


// =====================
// Task 2: Add & Update
// =====================
menuItem.isAvailable = true;
menuItem.price = 150;

console.log(menuItem);


// =====================
// Task 3: Method
// =====================
menuItem.describe = function () {
  console.log("☕ " + this.name + " costs ₹" + this.price + " and is a " + this.type + ".");
};

menuItem.describe();


// =====================
// Task 4: Constructor
// =====================
function MenuItem(name, price, type) {
  this.name = name;
  this.price = price;
  this.type = type;

  this.describe = function () {
    let emoji = "☕";
    if (this.type === "Snack") emoji = "🥪";
    if (this.type === "Dessert") emoji = "🍫";

    console.log(emoji + " " + this.name + " costs ₹" + this.price + " and is a " + this.type + ".");
  };
}

let latte = new MenuItem("Latte", 160, "Drink");
let sandwich = new MenuItem("Cheese Sandwich", 120, "Snack");

latte.describe();
sandwich.describe();


// =====================
// Task 5: Array of Objects
// =====================
let menu = [
  new MenuItem("Latte", 150, "Drink"),
  new MenuItem("Espresso", 120, "Drink"),
  new MenuItem("Brownie", 100, "Dessert")
];

for (let item of menu) {
  item.describe();
}

