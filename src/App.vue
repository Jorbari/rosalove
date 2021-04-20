<template>
  
 <body id="App">
    

    <div class="nav__bar">
        <section class="nav__bar__logo__name">
            <h3>
                <span>Rosalove.</span>
                <!-- <span>ai</span> -->
            </h3>
        </section>
        <!-- <section class="nav__bar__links">
            <ul>
                <li>Contact Us</li>
                <li>FAQs</li>
            </ul>
        </section> -->
    </div>

    <div class="content content__top">

        <section class="content__heading">
            <h1>
                <span>Expressing Deep Love</span>
                <span>in Words</span>
            </h1>
            <span class="under__love">
                <svg width="159" height="24" viewBox="0 0 159 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M1.55124 12.3357C0.63206 12.5835 0.0878353 13.5296 0.335679 14.4488C0.583523 15.3679 1.52958 15.9122 2.44876 15.6643L1.55124 12.3357ZM147.644 10.32C148.575 10.5167 149.49 9.92106 149.687 8.9896C149.883 8.05814 149.288 7.14358 148.356 6.94688L147.644 10.32ZM2.44876 15.6643C27.4536 8.92211 78.5704 -4.26656 147.644 10.32L148.356 6.94688C78.4854 -7.80807 26.7364 5.54485 1.55124 12.3357L2.44876 15.6643Z" fill="#DB342B" fill-opacity="0.8"/>
                    <path opacity="0.16" d="M11.5513 20.3366C10.6326 20.5863 10.0903 21.5334 10.34 22.4521C10.5897 23.3708 11.5368 23.9131 12.4555 23.6634L11.5513 20.3366ZM156.644 18.2788C157.575 18.4766 158.49 17.8819 158.688 16.9507C158.886 16.0194 158.291 15.1042 157.36 14.9065L156.644 18.2788ZM12.4555 23.6634C37.2861 16.9145 88.0448 3.7127 156.644 18.2788L157.36 14.9065C87.9581 0.169914 36.563 13.5384 11.5513 20.3366L12.4555 23.6634Z" fill="white"/>
                    </svg>
            </span>
        </section>

        <section class="content__description">
            <p>
                An <span>AI</span> that generates unique, personalized and beautiful love
                letters for your partner with no plagiarism
            </p>
        </section>

        <section class="content__search">

            <input type="text" v-model="readername" placeholder="Message for?  e.g “My girlfriend”">
            <button @click="getletter()">Generate</button>

        </section>


    </div>

    <div class="content content__bg">

        <div class="content__cards" v-if="showcard == true"  >

            <section class="card" :key="letter.id" v-for="letter in letters">
                
                <p>
                    <span>
                        <svg width="42" height="36" viewBox="0 0 42 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path opacity="0.4" fill-rule="evenodd" clip-rule="evenodd" d="M13.9764 5.14286V0C9.29389 1.15831 5.79393 3.77604 3.47635 7.85328C1.15877 11.9305 0 17.4671 0 24.4633V36H15.75V20.5714H9.01013V18.973C9.01013 15.2201 9.42398 12.1969 10.2517 9.90347C11.0794 7.61003 12.3209 6.02317 13.9764 5.14286ZM40.2264 5.14286V0C35.5439 1.15831 32.0439 3.77604 29.7264 7.85328C27.4088 11.9305 26.25 17.4671 26.25 24.4633V36H42V20.5714H35.2601V18.973C35.2601 15.2201 35.674 12.1969 36.5017 9.90347C37.3294 7.61003 38.5709 6.02317 40.2264 5.14286Z" fill="#E0B03C"/>
                            </svg>
                    </span>
                    <span>
                    <i class="red">{{'Dear '+ readername+ '! '}}</i> {{letter}}
                    </span>
                    <span>
                        <svg width="42" height="36" viewBox="0 0 42 36" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path opacity="0.4" fill-rule="evenodd" clip-rule="evenodd" d="M28.0236 30.8571V36C32.7061 34.8417 36.2061 32.224 38.5236 28.1467C40.8412 24.0695 42 18.5329 42 11.5367L42 0H26.25L26.25 15.4286L32.9899 15.4286V17.027C32.9899 20.7799 32.576 23.8031 31.7483 26.0965C30.9206 28.39 29.6791 29.9768 28.0236 30.8571ZM1.77365 30.8571V36C6.4561 34.8417 9.95607 32.224 12.2736 28.1467C14.5912 24.0695 15.75 18.5329 15.75 11.5367V0L0 0L0 15.4286H6.73986V17.027C6.73986 20.7799 6.32602 23.8031 5.49831 26.0965C4.6706 28.39 3.42906 29.9768 1.77365 30.8571Z" fill="#E0B03C"/>
                            </svg>
                            
                    </span>
                </p>

                <section class="share">

                    <button @click="tweetletter(letter)">Tweet</button>
                    <button @click="coypletter(letter)">Copy Text</button>

                </section>

            </section>
        </div>
    </div>
    
    <!-- <a class="contributor" href="https://twitter.com/Jorbari2" target="_blank">
      <span>
          <svg
          version="1.1"
          id="Capa_1"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 112.197 112.197"
          style="enable-background: new 0 0 112.197 112.197"
          xml:space="preserve"
        >
          <g>
            <circle style="fill: #55acee" cx="56.099" cy="56.098" r="56.098" />
            <g>
              <path
                style="fill: #f1f2f2"
                d="M90.461,40.316c-2.404,1.066-4.99,1.787-7.702,2.109c2.769-1.659,4.894-4.284,5.897-7.417
			c-2.591,1.537-5.462,2.652-8.515,3.253c-2.446-2.605-5.931-4.233-9.79-4.233c-7.404,0-13.409,6.005-13.409,13.409
			c0,1.051,0.119,2.074,0.349,3.056c-11.144-0.559-21.025-5.897-27.639-14.012c-1.154,1.98-1.816,4.285-1.816,6.742
			c0,4.651,2.369,8.757,5.965,11.161c-2.197-0.069-4.266-0.672-6.073-1.679c-0.001,0.057-0.001,0.114-0.001,0.17
			c0,6.497,4.624,11.916,10.757,13.147c-1.124,0.308-2.311,0.471-3.532,0.471c-0.866,0-1.705-0.083-2.523-0.239
			c1.706,5.326,6.657,9.203,12.526,9.312c-4.59,3.597-10.371,5.74-16.655,5.74c-1.08,0-2.15-0.063-3.197-0.188
			c5.931,3.806,12.981,6.025,20.553,6.025c24.664,0,38.152-20.432,38.152-38.153c0-0.581-0.013-1.16-0.039-1.734
			C86.391,45.366,88.664,43.005,90.461,40.316L90.461,40.316z"
              />
            </g>
          </g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
          <g></g>
        </svg>
      </span>

      <p>@Jorbari2</p>
    </a> -->
  
</body>
</template>

<script>
import axios from "axios";
export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      readername : null,
      showcard : false,
      letters : []
    }
  },

  methods:{
    coypletter(letter) {
      navigator.clipboard.writeText('Dear '+ this.readername+'! ' + letter);
    },

    tweetletter(letter){
      var text = 'Dear '+ this.readername+'! ' + letter;
      var url = "http://rosalove.xyz";
      window.open('http://twitter.com/share?url='+encodeURIComponent(url)+'&text='+encodeURIComponent(text), '', 'left=0,top=0,width=550,height=450,personalbar=0,toolbar=0,scrollbars=0,resizable=0');
    },

    set_letters(notes) {
      this.letters = notes;
    },
    getletter(){
      var baseURL = "https://rosalove-emekaborisama.cloud.okteto.net/loveletterlong";

      axios({
        method: "post",
        url: baseURL,
        headers: { "Content-Type": "multipart/form-data" },
      })
        .then((response) => {
          this.set_letters(response.data.result);
          this.showcard = true;
          console.log(response.data);
        })
        .catch((e) => {
          console.log(e);
        });
    }
  }
}
</script>

<style lang="scss">
  @import './assets/sass/main.scss';
</style>
