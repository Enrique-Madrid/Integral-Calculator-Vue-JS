<template>
    <transition name="slide-fade">
        <div v-if="alert">
            <div class="h-screen"> 
                <div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-lg flex items-center space-x-4 alert my-16">
                    <h1 class="text-red-600 text-bold">This program is under development, not all functions are available D:</h1>
                    <button class="py-8 px-4 btn rounded" @click="alert = !alert"><h1>ok</h1></button>
                </div>
            </div>
        </div>
    </transition>
</template>

<script>
    export default {
        name: "alertFrame",
        data() {
            return {
                alert: true,
            };
        },
    }
</script>

<style scoped>

.btn
{
    font-size: 40px;
    color: rgb(1, 1, 145);
    text-align: center;
    font-weight: lighter;

}

.btn:hover
{
    background-color: rgb(1, 1, 145);
    color: #ffffff;
}

h1, a
{
    font-family: 'Silkscreen', cursive;
}

.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
{
  transform: translateX(10px);
  opacity: 0;
}

</style>