<template>
  <div>
    <el-container>
      <el-header>
        <el-tabs :tab-position="tabPosition" v-model="activeName">
          <el-tab-pane label="总览" name="summary" :key="'first'">
            <template>
              <div class="main">
                <div id="maintop">
                  <div id="maintop1">
                    <LineChart />
                  </div>
                  <div id="maintop2">
                    <BarChart />
                  </div>
                </div>
                <div id="mainbottom">
                  <SankeyChart />
                </div>
              </div>
            </template>
          </el-tab-pane>
          <el-tab-pane label="桑基图" name="sankey" :key="'second'">
            <template>
              <div class="main">
                <SankeyChart />
              </div>
            </template>
          </el-tab-pane>
          <el-tab-pane label="折线图" name="line" :key="'third'">
            <template>
              <div class="display">
                <LineChart
                  style="
                    width: 1000px;
                    position: relative;

                    margin-left: -200px;
                  "
                />
              </div>
            </template>
          </el-tab-pane>
          <el-tab-pane label="饼图" name="bar" :key="'fourth'">
            <template>
              <div class="display">
                <BarChart />
              </div>
            </template>
          </el-tab-pane>
          <el-tab-pane label="一周学习汇报" name="result" :key="'fifth'">
            <template>
              <div
                class="display"
                style="position: relative; left: 50%; margin-left: -660px"
              >
                <LearningResult />
              </div>
            </template>
          </el-tab-pane>
        </el-tabs>
      </el-header>
    </el-container>
  </div>
</template>

<script>
import SankeyChart from "./components/SankeyChart.vue";
import LineChart from "./components/LineChart.vue";
import BarChart from "./components/BarChart.vue";
import LearningResult from "./components/LearningResult.vue";

export default {
  name: "App",
  components: {
    SankeyChart,
    LineChart,
    BarChart,
    LearningResult,
  },
  data() {
    return {
      tabPosition: "top",
      activeName: "first",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-x: scroll;
}

.el-header {
  background-color: #b3c0d1;
  color: #778899;
  line-height: 60px;
}
.el-tabs__nav-scroll {
  margin-left: 70%;
}
.el-tabs__item {
  font-size: 24px;
}
.main {
  position: relative;
  left: 50%;
  margin-left: -650px;
  margin-top: 60px;
}
.display {
  position: relative;
  left: 50%;
  margin-left: -300px;
  margin-top: 60px;
}
#maintop {
  display: flex;
  margin-bottom: 50px;
}
#maintop2 {
  padding-left: 30px;
}
</style>
