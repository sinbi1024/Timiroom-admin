<script lang="ts">
import {defineComponent, nextTick, onMounted, ref} from "vue";

export default defineComponent({
  name: "service",
  setup() {
    const width = window.innerWidth;
    const scrollValue = ref<number>(0);
    const scrollEvent = () => {
      const scroll = addEventListener('scroll', () => {
        scrollValue.value = window.scrollY;
        console.log("service: ", scrollValue.value);
      })
    }

    onMounted(() => {
      scrollEvent();
      const v = document.getElementsByClassName('service-card');
      console.log('client height : ', v);
      // console.log('client height : ', v[0].offsetTop);
      nextTick(() => {
      })
    })

    return {
      width,
      scrollValue,
    }
  }
})
</script>

<template>
  <article class="service">
    <div class="user-wrap">
      <div class="user-img-service">
      </div>
      <div class="user-text">
        <span class="inner-text">Service for Smart Factory</span><br>
        <div class="inner-sub-text">스마트 팩토리에 최적화된 모니터링 시스템을 제공합니다.</div>
      </div>
    </div>

    <section>
      <p>* 아래 이미지들은 실제 구현 화면과 다소 차이가 있음을 알려 드립니다.</p>
      <div
          :class="width > 520 && scrollValue > 220 ? 'slide-left-action' : width <= 520 && scrollValue > 0 ? 'slide-left-action' : 'slide-left-actived'">
        <div class="service-card">
          <img class="monitoring-of-product">
          <div
              :class="width > 520 && scrollValue > 640 ? 'fade-actived' : width <= 520 && scrollValue > 90 ? 'fade-actived' : 'fade-action'">
            <div class="about">
              <div class="service-title">
                제품 정보
              </div>
              <div class="service-context">
                생산 공정에 필요한 품목 코드, 품목명, 생산일자와 같은<br>
                제품 정보를 표시해준다.
              </div>
            </div>
          </div>
        </div>
      </div>

      <div
          :class="width > 520 && scrollValue > 820 ? 'slide-left-action' : width <= 520 && scrollValue > 220 ? 'slide-left-action' : 'slide-left-actived'">
        <div class="service-card">
          <img class="monitoring-of-progress">
          <div
              :class="width > 520 && scrollValue > 1220 ? 'fade-actived' : width <= 520 && scrollValue > 440 ? 'fade-actived' : 'fade-action'">
            <div class="about">
              <div class="service-title">
                작업 진행 현황
              </div>
              <div class="service-context">
                설비의 가동 상태와 생산 공정에서 발생하는 데이터를<br>
                실시간으로 가져와 표시해준다.
              </div>
            </div>
          </div>
        </div>
      </div>

      <div
          :class="width > 520 && scrollValue > 1500 ? 'slide-left-action' : width <= 520 && scrollValue > 590 ? 'slide-left-action' : 'slide-left-actived'">
        <div class="service-card">
          <img class="monitoring-of-target">
          <div
              :class="width > 520 && scrollValue > 1830 ? 'fade-actived' : width <= 520 && scrollValue > 850 ? 'fade-actived' : 'fade-action'">
            <div class="about">
              <div class="service-title">
                생산 현황
              </div>
              <div class="service-context">
                관리자가 입력한 하루 생산 목표량과 현재 실시간 생산량을 표시하여<br>
                생산 실적을 파악할 수 있도록 한다.
              </div>
            </div>
          </div>
        </div>
      </div>

      <div
          :class="width > 520 && scrollValue > 2100 ? 'slide-left-action' : width <= 520 && scrollValue > 1005 ? 'slide-left-action' : 'slide-left-actived'">
        <div class="service-card">
          <img class="monitoring-of-environ">
          <div
              :class="width > 520 && scrollValue > 2445 ? 'fade-actived' : width <= 520 && scrollValue > 1230 ? 'fade-actived' : 'fade-action'">
            <div class="about">
              <div class="service-title">
                공장 환경
              </div>
              <div class="service-context">
                공장의 온도, 습도, 미세먼지 농도의 환경 데이터를<br>
                센서로부터 받아서 표시해준다.
              </div>
            </div>
          </div>
        </div>
      </div>

      <div
          :class="width > 520 && scrollValue > 2680 ? 'slide-left-action' : width <= 520 && scrollValue > 1390 ? 'slide-left-action' : 'slide-left-actived'">
        <div class="service-card">
          <img class="monitoring-of-total">
          <div
              :class="width > 520 && scrollValue > 3050 ? 'fade-actived' : width <= 520 && scrollValue > 1620 ? 'fade-actived' : 'fade-action'">
            <div class="about">
              <div class="service-title">
                종합 모니터링
              </div>
              <div class="service-context">
                요약적으로 표시될 필요가 있는 주요 데이터를 표시하고,<br>
                그로부터 산출한 통계적 결과를 제공한다.
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="bottom-margin"></div>
    </section>
  </article>
</template>