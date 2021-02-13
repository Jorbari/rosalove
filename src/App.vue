<template>
  
 <body id="App">
    

    <div class="nav__bar">
        <section class="nav__bar__logo__name">
            <h3>
                <span>Rosalove.</span><span>ai</span>
            </h3>
        </section>
        <section class="nav__bar__links">
            <ul>
                <li>Contact Us</li>
                <li>FAQs</li>
            </ul>
        </section>
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
                Generate unique, personalize and beautiful love
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
    
   <section class="contributor">

       <p>Jorbari &</p>
       <p>Stephanie</p>
   </section>
  
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
      var text = 'Dear '+ this.readername+'! ' + letter + '(From RosaLove.ai)';
      var url = "http://rosalove.ai";
      window.open('http://twitter.com/share?url='+encodeURIComponent(url)+'&text='+encodeURIComponent(text), '', 'left=0,top=0,width=550,height=450,personalbar=0,toolbar=0,scrollbars=0,resizable=0');
    },

    set_letters(notes) {
      this.letters = notes;
    },
    getletter(){
      var baseURL = "https://rroo-y2w9w.ondigitalocean.app/loveletterlong";

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

<style>
@import './assets/css/style.css';
</style>
