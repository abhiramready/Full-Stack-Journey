# 2. JavaScript Algorithms and Data Structures Certification
 
 ✅ FreeCodeCamp Certified

 🎯 Topics covered
 
 * Basic JavaScript, ES6
 * Object-oriented programming 
 * Regular Expressions, Debugging
 * Basic Data Structures and Algorithms
 
## ✨ Projects

1. Palindrome Checker
2. Roman Numeral Converter
3. Caesars Cipher
4. Telephone Number Validator
5. Cash Register

## 1. Palindrome Checker

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

## 2. Roman Numeral Converter
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

## 3. Caesars Cipher
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

## 4. Telephone Number Validator
```javascript
function telephoneCheck(str) {
  return (/^(1\s?)?(\(\d{3}\)|\d{3})[\s\-]?\d{3}[\s\-]?\d{4}$/).test(str);
}

telephoneCheck("555-555-5555");
```

## 5. Cash Register
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
