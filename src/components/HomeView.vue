<template>
   <header class="head bg-[#313536] h-24 flex items-center sticky top-0 z-10">
      <div class="container flex items-center justify-between">

            <div class="logo flex items-center gap-2">
               <img src="../assets/images/logo.svg" alt="err">
               <h3 class="text-white text-3xl">Asco.Dev</h3>
            </div>

            <div class="menu">
               <ul class="links flex items-center justify-center gap-10">
                  <li class="link">
                     <a class="text-white text-2xl transition-all hover:text-green-500 hover:border-green-500 hover:border-b-4 pb-1" href="">Home</a>
                  </li>
                  <li class="link">
                     <a href="" class="text-white transition-all text-2xl hover:text-green-500 hover:border-green-500 hover:border-b-4 pb-1">About</a>
                  </li>
                  <li class="link">
                     <a href="" class="text-white transition-all text-2xl hover:text-green-500 hover:border-green-500 hover:border-b-4 pb-1">Skills</a>
                  </li>
                  <li class="link">
                     <a href="" class="text-white transition-all text-2xl hover:text-green-500 hover:border-green-500 hover:border-b-4 pb-1">Clients</a>
                  </li>
                  <li class="link">
                     <a href="" class="text-white transition-all text-2xl hover:text-green-500 hover:border-green-500 hover:border-b-4 pb-1">Blog</a>
                  </li>
               </ul>
            </div>

            <div class="contact-us">
               <button class="text-white transition-all  bg-green-500 py-2 px-7 rounded-lg hover:bg-green-600">Contact</button>
            </div>

      </div>
   </header>

   <section class="hero bg-[#252829]">
      <div class="container flex items-center justify-between">
         <div class="text-content">
            <h2 class="title text-5xl text-white flex flex-col gap-5">
               Hello I'm <span class="text-[#00E472]">{{ text }}</span>
            </h2>

            <p class="text-[#808080] mt-3">Web Developer in Tashkent</p>

            <div class="btns mt-6 flex gap-7">
               <button class="btn text-white transition-all  bg-green-500 py-2 px-10 rounded-3xl hover:bg-green-600">About Me</button>
               <button class="btn border border-green-600 py-2 px-10 rounded-3xl text-white hover:bg-green-500">Contact</button>
            </div>
         </div>

         <div class="img-content relative">
            <img class="relative left-6 bottom-9 w-[470px]" src="../assets/images/hero-img.svg" alt="err">
         </div>
      </div>
   </section>

   <section class="about bg-[#313536] pt-16">
      <div class="container flex items-center justify-around">
         <div class="img-content">
            <img src="../assets/images/about-img.png" alt="err">
         </div>

         <div class="text-contet">
            <span class="text-green-500">ABOUT ME</span>

            <h2 class="text-white text-4xl mt-4">Front End Developer</h2>

            <p class="text-[#ABAEB0] text-2xl w-[650px] mt-6">I am Sharifov Aslbek, I was born on July 17, 2009, I am 15 years old, I completed the Front End course at the Itlabs training center, my experience is 1 month.</p>
            <p class="text-[#ABAEB0] text-2xl w-[650px] mt-6">My strengths: Problem solving and writing beautiful code to finish projects faster and better</p>
         </div>
      </div>
   </section>

   <section class="sides bg-[#252829] py-10">
      <div class="container flex justify-between items-center gap-10">
         <div class="text-content flex flex-col gap-10">
            <h2 class="text-white text-4xl w-[420px]">I am a Web developer. And I execl at what I do.</h2>
            <p class="text-[#ABAEB0] w-[650px]">The quick brown fox jumps over the lazy dog. It is the goto line for learning touch tpying. I use this line quite often. And It is very helpful. Someone came up with this brillient line and help probably a million people</p>
         </div>

         <div class="skills flex justify-center flex-wrap gap-5">
            <div class="one w-[190px] h-[190px] rounded-full border-8 flex items-center justify-center border-green-500 text-white">
               <h3>Html/Css</h3>
            </div>

            <div class="two w-[190px] h-[190px] rounded-full border-8 flex items-center justify-center border-green-500 text-white">
               <h3>Sass/Scss</h3>
            </div>

            <div class="three w-[190px] h-[190px] rounded-full border-8 flex items-center justify-center border-green-500 text-white">
               <h3>Tailwind/Bootstrap</h3>
            </div>

            <div class="four w-[190px] h-[190px] rounded-full border-8 flex items-center justify-center border-green-500 text-white">
               <h3>Js/Vuejs/Vuex</h3>
            </div>
         </div>
      </div>
   </section>

   <footer class="footer bg-[#191a1b] py-2">
      <div class="container flex items-center justify-center">
         <h2 class="text-[#ABAEB0]">Designed by <span class="text-green-500">Sharifov Aslbek</span></h2>
      </div>
   </footer>
</template>

<script>
export default {
   data() {
      return {
         wordIndex: 0,
         charIndex: 0,
         isDeleting: false,
         words: ["Front End Developer" , "Sharifov Aslbek"],
         text: '',
      }
   },
   methods: {
      typeEffect() {
         const currentWord = this.words[this.wordIndex];
         const currentChar = currentWord.substring(0 , this.charIndex);
         this.text = currentChar;
   if(!this.isDeleting && this.charIndex < currentWord.length) {
      this.charIndex++
      setTimeout(this.typeEffect, 200);
   } else if(this.isDeleting && this.charIndex > 0) {
      this.charIndex--
      setTimeout(this.typeEffect, 100);
   } else {
      this.isDeleting = !this.isDeleting
      this.wordIndex = !this.isDeleting ? (this.wordIndex + 1) % this.words.length : this.wordIndex;
      setTimeout(this.typeEffect , 1200)
   }
      }
   } ,
   mounted() {
      this.typeEffect()
   },
}
</script>

<style></style>