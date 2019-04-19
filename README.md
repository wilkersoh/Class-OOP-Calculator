# 计算机

### this.currentOperand
<p>这个是输入的号码的地方</p>

###  this.previousOperand
<p>这个是+ - *  /后输入之前号码的地方</p>

### compute()
<p>算法，没有等于空就把他们算起来</p>

### delete()
<p>注意： slice 没算最后一个的</p>

``` javascript
// 从0 index 到 最后1个 但最后一个不包括里面
this.currentOperand.toString().slice(0, -1);
```

### this.currentOperand
<p>任何计算机里的行动都会储存进currentOperand过后 把它的值render去html</p>

``` javascript
updateDisplay(){
    this.currentOperandTextElement.innerText = this.currentOperand
}
```

### toLocaleString('en')
<p>最后使用这个方法让他显示逗号 > 3,000</p>

``` javascript
getDisplayNumber(number){
    const floatNumber = parseFloat(number);
    if(isNaN(floatNumber)) return '';
    return floatNumber.toLocaleString('en');
}
```

### getDisplayNumber()
<p>这个也是转换去逗号但是他还帮助就算没有数字也能放.先</p>

``` javascript
    getDisplayNumber(number){
        const stringNumber = number.toString();
        // turn to array
        const integerDigits = parseFloat(stringNumber.split('.'));
        const decimalDigits = stringNumber.split('.')[1];
        let integerDisplay;

        if(isNaN(integerDigits)){
            integerDisplay = '';
        }else{
            integerDisplay = integerDigits.toLocaleString('en', {
                maximumFractionDigits: 0
            });
        }

        if(decimalDigits != null){
            return `${integerDisplay}.${decimalDigits}`
        } else {
            return integerDisplay
        }
    }
```