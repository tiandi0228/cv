<template>
  <div class="loading" v-show="!loading">
    <div class="spinner">
        <div class="rect1"></div>
        <div class="rect2"></div>
        <div class="rect3"></div>
        <div class="rect4"></div>
        <div class="rect5"></div>
    </div>
  </div>
  <div class="main-container" v-show="loading" style="display: none;">
    <section class="section section-header">
      <div class="section-bg section-header-bg"></div>
      <div class="section-bg section-content-bg"></div>
      <div class="container">
        <header class="header">
          <div class="header-box">
            <div class="avatar wow inShow no-print">
              <img src="/assets/images/pic.jpg" alt="logo" class="img-responsive">
            </div>
            <h1 class="name text-center wow inShow no-print">{{userInfo.nickname}}</h1>
            <h1 class="name text-center hide show-print-block">{{userInfo.name}}</h1>
          </div>
        </header>
        <div class="section-content">
          <div class="content-box">
            <div class="name-slogan">
              <h2 class="wow inShow" data-wow-delay="0.1s">
                <span class="text-light">{{userInfo.lastName}}</span>&nbsp;{{userInfo.firstName}}
              </h2>
              <div class="description wow inShow" data-wow-delay="0.15s">{{userInfo.slogan}}</div>
            </div>
            <div class="contact-info">
              <div class="row">
                <div class="col-md-6 col-lg-3">
                  <div class="item wow inShow" data-wow-delay="0.3s">
                    <h4>Location</h4>
                    <address>{{userInfo.location}}</address>
                  </div>
                </div>
                <div class="col-md-6 col-lg-3">
                  <div class="item wow inShow" data-wow-delay="0.45s">
                    <h4>QQ</h4>
                    <div class="info">{{userInfo.qq.number}}</div>
                  </div>
                </div>
                <div class="col-md-6 col-lg-3">
                  <a class="item wow inShow" data-wow-delay="0.5s" href="{{userInfo.website}}" target="_blank">
                    <h4>Website</h4>
                    <div class="info">{{userInfo.website}}</div>
                  </a>
                </div>
                <div class="col-md-6 col-lg-3">
                  <a class="item wow inShow" data-wow-delay="0.55s" href="mailto:{{userInfo.email}}">
                    <h4>Email</h4>
                    <div class="info">{{userInfo.email}}</div>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <div class="section-bg section-header-bg"></div>
        <div class="section-bg section-content-bg"></div>
        <header class="header">
          <div class="content-box">
            <h2 class="title">介绍&nbsp;/&nbsp;<small><i>Intro</i></small></h2>
            <div class="description">介绍一些个人基本情况</div>
          </div>
        </header>
        <div class="section-content">
          <div class="intro">
            <p v-for="intro in userInfo.intro">{{{intro}}}</p>
          </div>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <div class="section-bg section-header-bg"></div>
        <div class="section-bg section-content-bg"></div>
        <header class="header">
          <div class="content-box">
            <h2 class="title">经验&nbsp;/&nbsp;<small><i>Experience</i></small></h2>
            <div class="description">不同时期简短的从业经历介绍</div>
          </div>
        </header>
        <div class="section-content">
          <div class="experience">
            <div class="item" v-for="e in userInfo.experience">
              <div class="row">
                <div class="col-md-5">
                  <div class="time">{{e.time}}</div>
                  <div class="title">{{e.title}}</div>
                  <div class="description">{{e.intro}}</div>
                </div>
                <div class="col-md-7">{{e.description}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <div class="section-bg section-header-bg"></div>
        <div class="section-bg section-content-bg"></div>
        <header class="header">
          <div class="content-box">
            <h2 class="title">技能&nbsp;/&nbsp;<small><i>Skills</i></small></h2>
            <div class="description">我所掌握的工具和技术栈</div>
          </div>
        </header>
        <div class="section-content">
          <div class="row skill">
            <div class="col-md-6" v-for="s in userInfo.skill">
              <div class="item">
                <div class="text-info">
                  <span class="num text-light">{{s.percent}}</span>{{s.name}}
                </div>
                <div class="progress">
                  <div class="progress-bar wow progressShow" style="width:{{s.percent}}"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section no-print">
      <div class="container">
        <div class="section-bg section-header-bg"></div>
        <div class="section-bg section-content-bg"></div>
        <header class="header">
          <div class="content-box">
            <h2 class="title">联系&nbsp;/&nbsp;<small><i>Contact</i></small></h2>
            <div class="description">通过这些信息可以联系到我</div>
          </div>
        </header>
        <div class="section-content">
          <div class="contact">
            <div class="row">
              <div class="col-md-6 col-lg-3">
                <div class="item">
                  <h4>Location</h4>
                  <address>{{userInfo.location}}</address>
                </div>
              </div>
              <div class="col-md-6 col-lg-3">
                <div class="item">
                  <h4>QQ</h4>
                  <div class="info">{{userInfo.qq.number}}</div>
                </div>
              </div>
              <div class="col-md-6 col-lg-3">
                <a class="item" href="{{userInfo.website}}" target="_blank">
                  <h4>Website</h4>
                  <div class="info">{{userInfo.website}}</div>
                </a>
              </div>
              <div class="col-md-6 col-lg-3">
                <a class="item" href="mailto:{{userInfo.website}}">
                  <h4>Email</h4>
                  <div class="info">{{userInfo.email}}</div>
                </a>
              </div>
            </div>
          </div>
          <div class="name-slogan">
            <h2 class="wow inShow">
              <span class="text-light">{{userInfo.lastName}}</span>&nbsp;{{userInfo.firstName}}
            </h2>
            <div class="description wow inShow" data-wow-delay="0.05s">{{userInfo.slogan}}</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
var apiURL= '/assets/resume.json'
export default {
    data () {
      return {
        loading:false,
        userInfo:null,
      }
    },
    ready() {
        this.$http.get(apiURL).then(function(res) {
            this.userInfo = res.data
            this.loading = true
        })
    }
}
</script>

<style lang='sass'>
@import "assets/scss/style.scss";
</style>