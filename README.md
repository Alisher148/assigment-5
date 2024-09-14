// Q1: Create a function that takes an array, an index, and a value as parameters. 
// Inside the function, use the splice method to insert the value at the specified index in the array. 
// Return the modified array.
function insertValue<T>(array: T[], index: number, value: T): T[] {
    array.splice(index, 0, value);  // Using splice to insert the value at the specified index
    return array;  // Return the modified array
}

// Q2: Implement a simple shopping cart program using an array. 
// Create functions to add items, remove items, and update quantities using the splice method. 
// Print the cart's contents after each operation.
class ShoppingCart {
    private items: { name: string, quantity: number }[] = [];

    addItem(name: string, quantity: number): void {
        this.items.push({ name, quantity });
        console.log('Item added:', this.items);
    }

    removeItem(index: number): void {
        this.items.splice(index, 1);
        console.log('Item removed:', this.items);
    }

    updateItem(index: number, quantity: number): void {
        if (index >= 0 && index < this.items.length) {
            this.items[index].quantity = quantity;
            console.log('Item updated:', this.items);
        } else {
            console.log('Invalid index');
        }
    }
}

const cart = new ShoppingCart();
cart.addItem('Apple', 3);
cart.addItem('Banana', 2);
cart.updateItem(0, 5);
cart.removeItem(1);

// Q3: Write a program that uses a while loop to print the first 25 integers.
let i = 1;
while (i <= 25) {
    console.log(i);
    i++;
}

// Q4: Write a program that uses a while loop to print the first 10 even numbers.
let j = 0;
let count = 0;
while (count < 10) {
    if (j % 2 === 0) {
        console.log(j);
        count++;
    }
    j++;
}

// Q5: Create a function that takes a positive integer as parameter and uses a while loop 
// to calculate and return the factorial of that number.
function factorial(n: number): number {
    let result = 1;
    while (n > 1) {
        result *= n;
        n--;
    }
    return result;
}

console.log(factorial(5));  // Output: 120

// Q6: Write a program having an array of numbers. If the number is negative, 
// it should remove the negative number from the array.
const numbers = [1, -2, 3, -4, 5];
for (let k = 0; k < numbers.length; k++) {
    if (numbers[k] < 0) {
        numbers.splice(k, 1);
        k--;  // Adjust the index after removal
    }
}
console.log(numbers);  // Output: [1, 3, 5]

// Q7: Create a function that takes an array of numbers as parameter. 
// Use a while loop to calculate and return the sum of all the numbers in the array.
function sumArray(arr: number[]): number {
    let sum = 0;
    let index = 0;
    while (index < arr.length) {
        sum += arr[index];
        index++;
    }
    return sum;
}

console.log(sumArray([1, 2, 3, 4]));  // Output: 10

// Q8: Implement a program that takes a list of temperatures in Celsius as input from the user. 
// Convert each temperature to Fahrenheit using the formula F = (C * 9/5) + 32 and store the converted 
// temperatures in an array. Use a while loop to perform the conversion for each temperature.
const celsiusTemps = [0, 20, 30, 40];
const fahrenheitTemps: number[] = [];
let l = 0;
while (l < celsiusTemps.length) {
    const fahrenheit = (celsiusTemps[l] * 9/5) + 32;
    fahrenheitTemps.push(fahrenheit);
    l++;
}
console.log(fahrenheitTemps);  // Output: [32, 68, 86, 104]

// Q9: Write a program to remove all the odd numbers from an array.
const numArray = [1, 2, 3, 4, 5, 6];
for (let m = 0; m < numArray.length; m++) {
    if (numArray[m] % 2 !== 0) {
        numArray.splice(m, 1);
        m--;  // Adjust the index after removal
    }
}
console.log(numArray);  // Output: [2, 4, 6]
