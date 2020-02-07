<template>
    <section class="flex flex-col items-center justify-center h-screen">
        <div class="mb-6">
            <h2 class="text-2xl">{{ excuse }}</h2>
        </div>
        <div>
            <button type="button"
                    class="bg-white border-2 border-purple-500 text-purple-500 font-bold px-4 py-2 rounded text-white hover:bg-purple-500 hover:text-white"
                    @click="selectRandomSentence">
                Generate excuse
            </button>
        </div>
    </section>
</template>
<script>
    export default {
        data() {
            return {
                excuses: [
                    'CFDT people are burning my house',
                    'I broke my toe',
                    'My boiler is out of service',
                    'My son is sick',
                    'My wife fell in the Loire river',
                    'Someone stole my bike and destroyed my car',
                    'My dog ate my wife',
                    'My son kicked my ass and I can\'t walk',
                    'Sorry, I thought that it was a day off',
                    'I forgot that I was working for you',
                    'I am a "cadre", it\'s not about time but goals',
                    'My wife fell in the Loire river',
                    'Someone stole my bike and destroyed my car'
                ],
                excuse: ''
            };
        },
        methods: {
            selectRandomSentence() {
                let excuses = this.excuses.filter(s => s !== this.excuse);

                this.excuse = excuses[Math.floor(Math.random() * excuses.length)];
            }
        },
        mounted() {
            this.selectRandomSentence();
        }
    };
</script>
