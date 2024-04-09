<template>
<div class="container about-container">

    <div id="contactus">
        <h2>{{ $t("message.ContactHeading") }}</h2>
        <p v-html="$t('message.ContactEmail')"></p>
        <p v-html="$t('message.ContactText1')"></p>
        <p v-html="$t('message.ContactText2')"></p>
        <p v-html="$t('message.ContactText3')"></p>
    </div>

    <hr>
    <footer class="about-footer">
        <div class="privacy-policy-link">
            <router-link to="">{{ $t("message.PrivacyPolicy") }}</router-link>
        </div>
    </footer>

</div>

 <!-- /container -->
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({
  components: {
  },
})
export default class AboutComponent extends Vue {


    public scroll(divId: string) {

        // window.console.log(`AboutComponent.scroll(divID: ${divId}) called`);

        const divTop = (document.getElementById(divId) as HTMLElement)
                            .getBoundingClientRect().top;

        const navHeight = (document.getElementById('navbar')as HTMLElement)
                                .clientHeight;

        // window.console.log(`divTop: ${divTop}`);
        window.scroll({
            top: divTop + window.scrollY - navHeight,
            left: 0,
            behavior: 'smooth',
        });
    }
}
</script>

<style>
    html {
        scroll-behavior: smooth;
    }

    .about-footer {
        margin-top: 30px;
        margin-bottom: 50px;
    }

    .about-container {
        margin-top: 2.5em;
    }

    .fluid-image {
        max-width: 100%;
        height: auto;
    }

    .privacy-policy-link {
        text-align: center;
        font-size: small;
    }
</style>
