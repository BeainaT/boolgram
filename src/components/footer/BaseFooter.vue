<template>
    <footer>
        <div class="footer_links py-3">
            <span v-for="link, index in footerLinks" :key="index">
                <a href="#" v-if="index !== 0">
                    · {{link}}
                </a>
                <a href="#" v-else>
                    {{link}}
                </a>
            </span>
        </div>
        <p>© 2022 INSTAGRAM FROM META</p>
    </footer>
</template>
<script>
export default {
    name: 'BaseFooter',
    data() {
        return {
            footerLinks: [
                'Informazioni', 
                'Assistenza', 
                'Stampa',
                'API',
                'Lavora con noi',
                'Privacy',
                'Condizioni',
                'Luoghi',
                'Lingua'
            ]
        }
    }
}
</script>
<style lang="">
    
</style>