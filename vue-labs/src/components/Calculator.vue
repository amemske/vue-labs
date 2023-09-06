<template>

<div class="container">
    <div class="display">
        <form action="submit" @submit.prevent="calculateValues">
            <input type="text" v-model="inputStr">
            <input type="submit" value="=">
           
        </form>

        <!-- {{ result }} -->
    </div>
    <div class="buttons">
        <div class="rows">
            <div class="col-auto">
                <button @click="updateDisplay('+')" class="btn">+</button>
                <button @click="updateDisplay('-')" class="btn">-</button>
                <button @click="updateDisplay('*')" class="btn">*</button>
                <button @click="updateDisplay('/')" class="btn">/</button>
                <button @click="clearDisplay()" class="btn">Clear</button>
            </div>
        <div class="rows">
            <div class="col-auto">
                <button @click="updateDisplay('1')"  class="btn">1</button>
                <button @click="updateDisplay('2')" class="btn">2</button>
                <button @click="updateDisplay('3')" class="btn">3</button>
            </div>
        </div>
        <div class="rows">
            <div class="col-auto">
                <button @click="updateDisplay('4')" class="btn">4</button>
                <button @click="updateDisplay('5')" class="btn">5</button>
                <button @click="updateDisplay('6')" class="btn">6</button>
            </div>
        </div>
        <div class="rows">
            <div class="col-auto">
                <button @click="updateDisplay('7')" class="btn">7</button>
                <button @click="updateDisplay('8')" class="btn">8</button>
                <button @click="updateDisplay('9')" class="btn">9</button>
            </div>
        </div>
    </div>
</div>
</div>

</template>

<script>
export default {
    name: 'App',
    data(){
        return {
            inputStr: '',
            result: '',
        }
        
    },
    methods: {
        updateDisplay(val){
            this.inputStr = this.inputStr + val
        },
        calculateValues(){
            this.result = eval(this.inputStr)
            this.inputStr = this.result;
        },
        clearDisplay(){
            this.inputStr = '';
        }
    }

//Let's walk through an example using the addition of "2" and "3":
// Initially, the inputStr property is empty.
// When the button with the value "+" is clicked, the updateDisplay method is called with the parameter "+".
// Inside the updateDisplay method, the existing value of inputStr (which is currently empty) is concatenated with the provided val. So, "2" + "+" results in the string "2+".
// The updated value of "2+" is then assigned back to the inputStr property.
// Now, if you were to repeat the process by clicking the button with the value "3", the updateDisplay method would be called with the parameter "3".
// The existing value of inputStr (which is now "2+") is concatenated with the provided val. So, "2+" + "3" results in the string "2+3".
// The updated value of "2+3" is assigned back to the inputStr property.
   
}


</script>

<style scoped>

</style>
