<template>
    <div class="flex justify-center py-16">
        <div class="md:w-1/8 mx-8 bg-white rounded-lg">
            <div class="p-4 text-right shadow-2xl">
                <a class="m-2 font-sans text-xs text-blue">{{result}}</a>
                <div class="flex flex-row">                        
                    <input type="text" class="flex-1 w-32 font-sans md:text-4xl text-blue" v-model="operation" >
                    <button class="p-5 font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center mx-2 rounded flex-none " v-if="button"><h1>=</h1></button>
                </div>
            </div>
            <div>
                <div class="grid grid-cols-4 grid-rows-4 shadow-2xl bg-white">
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center col-span-2" @click="onClick(operation)"><h1>AC</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick(operation)"><h1>Del</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('/')"><h1>/</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('cos(')"><h1>cos</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('sen(')"><h1>sen</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('tan(')"><h1>tan</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('*')"><h1>*</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('log(')"><h1>log</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('ln(')"><h1>ln</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('exp(')"><h1>exp</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('+')"><h1>+</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center " @click="onClick('^')"><h1>^</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('pi')"><h1>pi</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('.')"><h1>.</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('-')"><h1>-</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('(')"><h1>(</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick(')')"><h1>)</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('x')"><h1>X</h1></button>
                    <button class="md:p-5 p-4 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="numPad = !numPad"><h1>-></h1></button>
                </div>
                <div v-if="numPad">
                    <div class="grid grid-cols-3 grid-rows-3 shadow-2xl bg-white">
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('1')"><h1>1</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('2')"><h1>2</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('3')"><h1>3</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('4')"><h1>4</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('5')"><h1>5</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('6')"><h1>6</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('7')"><h1>7</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('8')"><h1>8</h1></button>
                        <button class="md:p-3 p-2 text-2xl font-sans md:text-4xl text-blue hover:bg-blue hover:text-white text-center" @click="onClick('9')"><h1>9</h1></button>
                        <h1 class="col-span-3 font-sans text-xs text-blue m-4">Define an integration domain</h1>
                    </div>
                    <div class="grid grid-cols-2 rounded-b shadow-2xl bg-white p-4 justify-items-center">    
                        <input type="text" class="text-2xl font-sans text-blue h-14 w-20 md:w-40" v-model="a">
                        <input type="text" class="text-2xl font-sans text-blue h-14 w-20 md:w-40" v-model="b">
                    </div>
                </div>
            </div>
        </div>
    </div>

</template>
<script>

export default {
    name: "calcFrame",
    data() {
        return {
            operation: '',
            num: '',
            result: 'Insert an operation',
            button: false,
            numPad: false,
            alert: true,
            a: 'Int A',
            b: 'Int B',
        };
    },
    methods: {
        
        onClick(op){
            if (op == '/' || op == '*'){
                /*Check if operation doesn't have a parentesis behind the cursor*/
                if (this.operation.substr(this.operation.length - 1, 1) != '('){
                    this.operation += op;
                }
            } else {
                this.operation += op;
            }
            if (this.result == 'Insert an operation'){
                this.result = '';
            }
            if (this.operation != ''){
                this.button = true;
            }
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
