<template>
  <div data-theme="bumblebee">
    <!-- 1 -->
    <div
      id="1"
      class="hero h-screen"
      :style="{ 'background-image': 'url(' + require('../assets/bg1.jpg') + ')' }"
    >
      <div class="hero-overlay bg-opacity-90"></div>
      <div class="text-center hero-content text-neutral-content ease duration-100">
        <div>
          <h1 class="mb-5 text-5xl font-bold">สุขสันต์วันครบรอบอายุ 21 ปี มีมี่! 🎊</h1>
          <button
            class="btn btn-lg btn-primary btn-outline"
            @click="goTo(2)"
          >มาฉลองวันนี้กัน คลิก! 💌</button>
        </div>
      </div>
    </div>
    <!-- 2 -->
    <div
      id="2"
      class="hero h-screen"
      :style="{ 'background-image': 'url(' + require('../assets/m10.jpg') + ')' }"
      data-theme="bumblebee"
    >
      <div class="hero-overlay bg-opacity-75"></div>
      <div class="hero-content text-neutral-content">
        <div class="relative mt-28">
          <img class="w-5/12 absolute -top-80 right-0 z-0" src="../assets/m10.jpg" alt="m10" />
          <div class="relative z-10">
            <h1 class="mb-5 text-5xl font-bold">วันเกิดปีนี้ 🎁</h1>
            <p class="mb-5 text-3xl font-semibold leading-relaxed">
              - ขอให้เธอมีความสุขมากๆ ประสบความสำเร็จในทุกๆเรื่อง ขอบคุณที่ให้กำลังใจ และอยู่ข้างกันมาโดยตลอด
              <br />มีมี่เป็นคนที่ตั้งใจทำอะไร มักจะทำสิ่งนั้นสำเร็จอยู่เสมอ รู้มั้ย 😉
            </p>
            <div class="w-full flex justify-end">
              <button class="btn btn-lg btn-primary" @click="goTo(3)">หน้าถัดไป</button>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- 3 -->
    <div id="3" class="hero bg-contain h-screen bg-accent">
      <div class="hero-overlay bg-opacity-75"></div>
      <div class="text-center hero-content flex-col text-neutral-content">
        <p class="text-4xl font-bold text-primary shadow-sm">คุณอาจไม่รู้ว่าตัวคุณน่ารักแค่ไหน</p>
        <p class="text-2xl font-bold text-primary shadow-sm">มาดูความสดใสของคุณกันนะ 🤩</p>
        <section class="relative flex justify-center items-center overflow-hidden section">
          <div
            class="w-10 absolute top-1/2 left-3 z-10 cursor-pointer select-none text-secondary md:left-4 hover:text-primary-content text-4xl hover:bg-secondary-focus"
            @click="prev"
          >&#10094;</div>
          <div
            class="w-10 absolute top-1/2 right-3 z-10 cursor-pointer select-none text-secondary md:right-4 hover:text-primary-content text-4xl hover:bg-secondary-focus"
            @click="next"
          >&#10095;</div>
          <button class="btn btn-lg btn-primary absolute bottom-10" @click="goTo(4)">ไปต่อ</button>
          <div
            v-for="(img,index) in img"
            :key="index"
            :class="[index === current ? 'opacity-100 transition duration-500 ease-in-out' : 'opacity-0 transition duration-500 ease-in-out']"
          >
            <img
              v-if="index === current"
              :src="require(`../assets/${img.src}`)"
              :alt="img.src"
              class="w-full h-auto"
            />
          </div>
        </section>
      </div>
    </div>
    <!-- 4 -->
    <div id="4" class="hero h-screen bg-yellow-200 hover:bg-yellow-300">
      <div class="hero-overlay bg-opacity-25"></div>
      <div class="hero-content text-neutral-content">
        <div>
          <img class="float-right w-1/2" src="../assets/m4.jpg" alt="m4" />
          <div class="flex flex-col justify-center h-screen space-y-2">
            <h1 class="text-5xl font-bold mb-5">เห็นรูปข้างขวานี้ไหม 🥳</h1>
            <p class="mb-5 text-3xl font-semibold leading-relaxed">
              รูปนี้มีมี่ยังเรียนม.ปลายไม่จบ แต่ใส่เสื้อกาวน์แล้ว... (แน่นอนว่าไอเจถ่าย 🤪)
              <br />ตอนนี้ก็เหมือนกัน ถึงมันจะเหนื่อยยาก ลำบาก
              <br />ต้องอดทนแค่ไหน
              <br />แต่เค้าก็จะเป็นกำลังใจให้เสมอ และมีมี่ก็จะผ่านมันไป
              <br />ได้เหมือนทุกครั้งแน่นอน 🥰
              <br />คนเก่งคนนี้
            </p>
            <button
              class="btn btn-lg btn-outline btn-primary self-end mr-5"
              @click="goTo(5)"
            >ถัดปายย</button>
          </div>
        </div>
      </div>
    </div>
    <!-- 5 -->
    <div id="5" class="hero h-screen bg-green-200">
      <div class="hero-overlay bg-opacity-95"></div>
      <div class="text-neutral-content">
        <div class="flex flex-row justify-start space-x-8">
          <div class="flex flex-col justify-center h-screen flex-grow">
            <div class="flex flex-row justify-center space-x-4">
              <img class="w-auto h-96" src="../assets/m2.jpg" alt="m2" />
              <img class="w-auto h-96" src="../assets/m3.jpg" alt="m2" />
            </div>
          </div>
          <div class="flex flex-col justify-center h-screen space-y-2">
            <h1 class="text-5xl font-bold mb-5">ไม่รู้เหมือนกัน</h1>
            <p class="mb-5 text-3xl font-semibold leading-relaxed">
              ว่าในรูปข้างๆนี้ (ไอเจถ่ายอีกแล้วๆๆ) มีมี่กำลังอธิษฐานอะไรอยู่...
              <br />แต่เจหวังว่า ทุกสิ่งที่มีมี่ปรารถนา มันจะต้องประสบผลสำเร็จ
              <br />ในอนาคตทุกอย่างแน่นอนนน
            </p>
            <button
              class="btn btn-lg btn-outline btn-primary self-end mr-5"
              @click="goTo(6)"
            >ถัดปายยอีกกนิดด</button>
          </div>
        </div>
      </div>
    </div>
    <!--  6 -->
    <div
      id="6"
      class="hero bg-contain h-screen"
      :style="{ 'background-image': 'url(' + require('../assets/m11.jpg') + ')' }"
    >
      <div class="text-center hero-content text-neutral-content ease duration-100">
        <div>
          <button class="btn btn-lg btn-primary" @click="goTo(7)">ไปต่อ</button>
        </div>
      </div>
    </div>
    <!-- 7 -->
    <div
      id="7"
      class="hero bg-contain h-screen"
      :style="{ 'background-image': 'url(' + require('../assets/m11.jpg') + ')' }"
    >
      <div class="hero-overlay bg-opacity-60"></div>
      <div class="text-center hero-content text-neutral-content ease duration-100">
        <div>
          <h1 class="mb-5 text-5xl font-bold">ลุงป้าสองคนนี้เขายืนทำไรกันนะ 🤪</h1>
          <button class="btn btn-lg btn-primary btn-outline" @click="goTo(8)">ต่อไปๆๆ</button>
        </div>
      </div>
    </div>
    <!-- 8 -->
    <div id="8" class="hero h-screen bg-accent-focus">
      <div class="hero-overlay bg-opacity-90"></div>
      <div
        class="text-center flex-col hero-content text-neutral-content ease duration-100 space-y-10"
      >
        <div class="flex flex-row justify-center section-2 space-x-4">
          <img class="w-full h-auto" src="../assets/m13.jpg" alt="m13" />
          <img class="w-full h-auto" src="../assets/m14.jpg" alt="m14" />
          <img class="w-full h-auto" src="../assets/m15.jpg" alt="m15" />
        </div>
        <div>
          <h1 class="text-3xl">น่ารัก สดใส เป็นที่รักของพ่อแม่ เพื่อนฝูง พี่น้องตลอดไปนะ คนเก่ง :D</h1>
          <h1 class="text-2xl">ด้วยความคิดถึง และห่วงใย ดูแลสุขภาพด้วยนะ</h1>
          <h1 class="text-xl">- ณัชนนท์ -</h1>
          <button class="btn btn-secondary" @click="goTo(1)">กลับสู่ด้านบน</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      current: 0,
      img: [
        { src: 'm8.jpg' },
        { src: 'm9.jpg' },
        { src: 'm12.jpg' }
      ]
    }
  },
  methods: {
    goTo(i) {
      document.getElementById(i).scrollIntoView({
        behavior: 'smooth'
      });
    },
    next() {
      if (this.current === this.img.length - 1) {
        this.current = 0
      } else {
        this.current += 1
      }
    },
    prev() {
      if (this.current === 0) {
        this.current = this.img.length - 1
      } else {
        this.current -= 1
      }
    }
  }
}
</script>

<style>
html {
  font-family: "Noto Sans Thai", sans-serif;
  /* overflow: hidden; */
}
.section {
  height: 800px;
  width: 600px;
}
.section-2 {
  height: 700px;
  width: 450px;
}
</style>