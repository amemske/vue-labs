<template>

    <div class="container">
        <div class="display">
            <form action="submit" @submit.prevent="calculateValues">
                <input type="text" v-model="inputStr">
                <input type="submit" value="=">
                <button @click="clearDisplay()" class="btn">Clear</button>
            </form>
    
            <!-- {{ result }} -->
        </div>
        <div class="buttons">
      <div v-for="row in buttonRows" :key="row" class="rows">
        <div class="col-auto">
          <button v-for="operation in row" :key="operation" @click="() => updateDisplay(operation)" class="btn">{{ operation }}</button>
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
                buttonRows: [
                    ['+', '-', '*', '/'],
                    ['1', '2', '3'],
                    ['4', '5', '6'],
                    ['7', '8', '9']
                ]
            }
            
        },
        methods: {
            updateDisplay(val){
                this.inputStr += val
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
    