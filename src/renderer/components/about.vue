<template>
    <v-layout row justify-center id="wrapper">
        <v-card>
            <v-card-title class="headline">About me</v-card-title>
            <v-card-text>
                <p>French 21 years old student and developer.</p>
                <p>Working on VueJs with Electron, Native-script this is a simple app for me to learn more about the real power of vuejs.</p>
                <p>Feel free to check out my social activity, this app is also available on my GitHub for Android and IOS</p>
                <v-btn icon href="https://github.com/Thomas-Philippot/" target="_blank">
                    <v-icon class="mx-3">fab fa-github</v-icon>
                </v-btn>
                <v-btn icon href="https://gitlab.com/Thomas_philippot" target="_blank">
                    <v-icon class="mx-3">fab fa-gitlab</v-icon>
                </v-btn>
                <v-btn icon href="https://twitter.com/Thomas_ph35" target="_blank">
                    <v-icon class="mx-3">fab fa-twitter</v-icon>
                </v-btn>
                <v-btn icon href="https://stackoverflow.com/users/7667135/thomas?tab=profile" target="_blank">
                    <v-icon class="mx-3">fab fa-stack-overflow</v-icon>
                </v-btn>

                <div class="text-xs-right">
                    <em class="mr-1"><small>Thomas Philippot</small></em>
                    <v-avatar
                            :size="50"
                    >
                        <img src="https://scontent-cdg2-1.xx.fbcdn.net/v/t1.0-9/20915442_1995801463988796_2991472233340304141_n.jpg?_nc_cat=0&oh=5bcf157a380176c6ce648f4b5499ee25&oe=5C0A496C" alt="avatar">
                    </v-avatar>
                </div>
                <hr class="my-3">
            </v-card-text>
        </v-card>
    </v-layout>
</template>

<script>
    export default {
      name: 'rm'
    }
</script>

<style scoped>

</style>
