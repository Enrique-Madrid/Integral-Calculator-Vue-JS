<template>
    <div class="background">
        <div class="inputArea" v-for="input in inputs" :key="input.id">
            <table>
                <tr>
                    <component-letter></component-letter>
                </tr>
            </table>
        </div>
    </div>
</template>
<script>
/*Import componentLetter.vue */
import componentLetter from './componentLetter.vue'

export default {

components: {
    componentLetter,
},

    name: "mainText",
    data() {
        return {
            txtH2: '',
            txtInput: '',
            counter: 0,
            inputs: [{
                id: 'letter0',
                label: 'Aquí iría el bkg',
                value: '',    
            }],
        };
    },
    methods: {
        addInput: function() {
            while (this.counter < 30) {
                this.counter++;
                this.inputs.push({
                    /*Wait a second*/
                    id: 'letter0' + this.counter,
                });
            }
        },
    },

    beforeMount(){
        this.addInput()
    },
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Silkscreen:wght@700&display=swap');

.background {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: #010191;
}

.inputArea th{
    font-family: 'Silkscreen', cursive;
    font-weight: mono medium;
    font-size: larger;
    color: white;
    /*Aplies blur in the font */
    filter: blur(0.7px);
    
}

/*.inputArea {
    display: flex;
    justify-content: center;
    flex-direction: column;
    background-color: rgb(1, 1, 145);
} */

</style>
