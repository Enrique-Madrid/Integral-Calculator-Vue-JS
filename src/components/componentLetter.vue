<template>
    <div class="div-parraf">
        <p>
            <span>{{msg}}</span>
        </p>
    </div>
</template>
<script>


export default {

    name: "mainText",
    data() {
        return {
            msg: 'Lol que onda xD',
            counter: 1,
        };
    },
    methods: {
        
        write(msg2){
            for (let i = 0; i < 1; i++) {
                this.msg += msg2[i];
                setTimeout(() => {
                    /*chose a random number */
                    let random = Math.floor(Math.random() * (10)) + 1;
                    msg2 = msg2.slice(0, -1);
                    this.msg += msg2[random];
                    this.msg = '';
                }, 1 * i);
            }
        },

        run: function() {
            /*Wait a second in vue js*/
            while(this.counter < 40) {
                this.counter++;
                setTimeout(() => {
                    this.write(this.msg);
                }, 1000);
            }
        }
    },

    mounted() {
        this.run();
    },
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.div-parraf
{
    width: 100%;
    height: 100%;
    text-align: center;
    vertical-align: middle;
    display: table-cell;
    font-size: auto;
    font-family: 'Silkscreen', cursive;
    color: rgb(1, 1, 145);
}
@import url('https://fonts.googleapis.com/css2?family=Silkscreen&display=swap');
h1
{   
    font-family: 'Silkscreen', cursive;
    font-size: 1em;
    color: white;
    font-weight: lighter;
    filter: blur(0.3px);
    justify-content: center;
}

</style>
