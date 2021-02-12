<template>
  <div>
    <b-tabs content-class="mt-3" fill class="tab">
      <!-- タブ：ログエクスポート -->
      <b-tab title="ログエクスポート" class="firsttab" active>
        <div class="selectbtn">
          駅名
          <b-form-select v-model="station" :options="options"></b-form-select>
          <!-- <div class="mt-3">駅名：{{ station }}</div> -->
        </div>
        <div class="selectmonth">
          年月
          <client-only>
            <datepicker
              :maximum-view="'month'"
              :minimum-view="'month'"
              :initial-view="'month'"
            ></datepicker>
            <!-- <template>
              <b-form-datepicker
                id="example-datepicker"
                v-model="mmdd"
                class="mb-2"
              ></b-form-datepicker>
            </template> -->
          </client-only>
        </div>

        <!-- ▼メインコンテンツ -->
        <div class="contents">
          {{ station }} {{ mmdd }}
          <b-button class="button">操作ログダウンロード</b-button>
        </div>
        <!-- ▲メインコンテンツ -->
      </b-tab>
      <!-- タブ：ログエクスポート -->
      <b-tab title="ログ一覧表示画面" class="secondtab">
        <p>一覧表示</p>
      </b-tab>
    </b-tabs>
  </div>
</template>

<script>
import Datepicker from 'vuejs-datepicker'
export default {
  components: {
    Datepicker,
  },
  data() {
    return {
      station: '駅を選択してください',
      options: [
        { value: '駅を選択してください', text: '駅を選択してください' },
        { value: '仙台駅', text: '仙台駅' },
        { value: '盛岡駅', text: '盛岡駅' },
        {
          value: '高輪ゲートウェイ駅',
          text: '高輪ゲートウェイ駅',
          disabled: true,
        },
      ],
      mmdd: '年月を選択してください',
    }
  },
}
</script>

<style scoped>
.tab {
  margin-top: 40px;
}

.selectbtn {
  width: 20%;
  margin: 40px;
}

.selectmonth {
  width: 20%;
  margin: 40px;
}

.contents {
  background-color: #efefef;
  margin: 40px;
  padding: 40px;
}

.button {
  background-color: black;
  margin-left: 40px;
}
</style>
