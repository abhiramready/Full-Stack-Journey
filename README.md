<h1 align="center">
	📚Full Stack Journey🚀
</h1>

## Certifications & Projects
1. [Responsive Web Designing Certification](https://github.com/abhiramready/Full-Stack-Journey#1-responsive-web-designing-certification)
2. [JavaScript Algorithms and Data Structures Certification](https://github.com/abhiramready/Full-Stack-Journey#2-javascript-algorithms-and-data-structures-certification)
3. [Front End Libraries Certification](https://github.com/abhiramready/Full-Stack-Journey#3-front-end-libraries-certification)

 ## 1. Responsive Web Designing Certification
 🎯 Topics covered
 
 * HTML, CSS basics
 * CSS Grid and Flexbox
 * Applied Visual Design and Acessibililty

## ✨ Projects 
* Click on projects to see live demo/code
### 1.1. Build a Tribute Page
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/TributePage.png)](https://codepen.io/abhiramready/full/WNrMaXV)

### 1.2. Build a Survey Form
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/FeedbackForm.png)](https://codepen.io/abhiramready/full/zYrWEQw)

### 1.3. Build a Product Landing Page
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/ProductLandingPage.png)](https://codepen.io/abhiramready/full/xxZaxVZ)

### 1.4. Build a Technical Documentaion Page
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/Technical%20Documentation.png)](https://codepen.io/abhiramready/full/vYLzQJZ)

### 1.5. Build a Personal Portfolio Page
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/PorfolioPage.png)](https://codepen.io/abhiramready/full/jOWejBK)

****

 ## 2. JavaScript Algorithms and Data Structures Certification
 🎯 Topics covered
 
 * Basic JavaScript, ES6
 * Object-oriented programming 
 * Regular Expressions, Debugging
 * Basic Data Structures and Algorithms
 
## ✨ Projects 
### 2.1  Palindrome Checker

```javascript
function palindrome(str) {
  const processedString=str
    .replace(/[\W_]/g,"")
    .toLowerCase();

  return (processedString===processedString
    .split("")
    .reverse()
    .join("")
  );
}

palindrome("eye");
```

### 2.2  Roman Numeral Converter
```javascript
function convertToRoman(num) {
  const decimalValue 
  = [1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1];
  const romanValue
  = ["M","CM","D","CD","C","XC","L","XL", "X","IX","V","IV","I"];

  let index=0
  let romanNumber = "";

  while(index < decimalValue.length) {
    while (decimalValue[index] <= num) {
      romanNumber +=romanValue[index];
      num -= decimalValue[index];
    }
     index++
  }
  return romanNumber;
}

convertToRoman(36);
```

### 2.3  Caesars Cipher
```javascript
function rot13(str) {
  return str
  .replace(/[A-Z]/g,(char)=> {
    return String.fromCharCode
   ((((char.charCodeAt() - 65 + 13) % 26) + 65))
  })
}

console.log(rot13("SERR PBQR PNZC"));
```

### 2.4  Telephone Number Validator
```javascript
function telephoneCheck(str) {
  return (/^(1\s?)?(\(\d{3}\)|\d{3})[\s\-]?\d{3}[\s\-]?\d{4}$/).test(str);
}

telephoneCheck("555-555-5555");
```

### 2.5  Cash Register
```javascript
const denomination = [
  { name: "ONE HUNDRED", value: 100.0 },
  { name: "TWENTY", value: 20.0 },
  { name: "TEN", value: 10.0 },
  { name: "FIVE", value: 5.0 },
  { name: "ONE", value: 1.0 },
  { name: "QUARTER", value: 0.25 },
  { name: "DIME", value: 0.1 },
  { name: "NICKEL", value: 0.05 },
  { name: "PENNY", value: 0.01 }
];

function checkCashRegister(price, cash, cid) {
  const output = { status: "", change: [] };
  let change = cash - price;

  const register = cid.reduce((acc, curr) => {
    acc[curr[0]] = curr[1];
    acc.total += curr[1];
    return acc;
  }, { total: 0 });

  if (register.total === change || change === 0) {
    output.status = "CLOSED";
    output.change = cid;
    return output;
  }

  if (register.total < change) {
    output.status = "INSUFFICIENT_FUNDS";
    return output;
  }

  const change_arr = denomination.reduce(function (acc, curr) {
    let value = 0;
    console.log(curr.name, ":", curr.value, "=", register[curr.name], "| Change :", change)
    while (register[curr.name] > 0 && change >= curr.value) {
      change -= curr.value;
      register[curr.name] -= curr.value;
      value += curr.value;
      console.log(curr.name, ":", curr.value, "=", register[curr.name], "| Change :", change, "| Value :", value)
      change = Math.round(change * 100) / 100;
    }
    if (value > 0) {
      acc.push([curr.name, value]);
    }
    return acc; 
  }, []);

  // If there are no elements in change_arr or we have leftover change, return
  // the string "Insufficient Funds"
  if (change_arr.length < 1 || change > 0) {
    output.status = "INSUFFICIENT_FUNDS";
    return output;
  }
  output.status = "OPEN";
  output.change = change_arr;
  return output;
}

console.log(checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]));
```

****
 ## 3. Front End Libraries Certification
 🎯 Topics covered
 
 * Sass
 * jQuery
 * Bootstrap
 * React and Redux
 
 
## ✨ Projects 
* Click on projects to see live demo/code

### 3.1. Build a Random Quote Machine
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/quote.png)](https://codepen.io/abhiramready/full/OJpmYVQ)

### 3.2. Build a Markdown Previewer
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/markdown.png)](https://codepen.io/abhiramready/full/QWpabLK)

### 3.3. Build a Drum Machine
[![](https://github.com/abhiramready/Full-Stack-Journey/blob/main/images/drum-machine.png)](https://codepen.io/abhiramready/full/poepVYb)
****
