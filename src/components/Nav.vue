<template>
  <v-content>
    <v-tabs :value="whichTab">
      <v-tabs-slider color="purple"></v-tabs-slider>
      <a href="http://heyri.net"><img src="../assets/logo_red_korean.png" alt="logo" height="40px"></a>
      <v-spacer></v-spacer>
      <v-tab
      v-for="(item, index) in items"
      :key="index"
      id="edit-1"
      >
        <v-menu open-on-hover bottom offset-y>
          <span slot="activator" color="primary" dark>{{item.title}}</span>
          <v-list>
            <v-list-tile v-for="(menu, index) in item.tabs" :key="index" @click="tabBtn(menu)">
              <v-list-tile-title><p class="title">{{ menu.title }}</p></v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>
      </v-tab>
      <v-tab id="edit-1" disabled>
        헤이리지도
      </v-tab>
    </v-tabs>
  </v-content>
</template>
<script>
export default {
  data() {
    return {
      show: false,
      active: null,
      items: [
        {
          title: '헤이리소개',
          tabs: [
            {title: '헤이리개요', link: '/blog/heyri/sub1.asp'},
            {title: '헤이리조직도', link: '/blog/heyri/sub1_1.asp'},
            {title: '휴-벨트 프로젝트', link: '/blog/heyri/sub1_7.asp'},
            {title: '제휴 및 후원안내', link: '/blog/heyri/sub1_3.asp'},
            {title: '헤이리촬영안내', link: '/blog/heyri/sub1_4.asp'},
            {title: '월요일오픈공간안내', link: '/blog/heyri/sub1_5.asp'},
            {title: '찾아오시는길', link: '/blog/heyri/sub1_6.asp'}]
        },{
          title: '헤이리소식',
          tabs: [
            { title: '헤이리소식', link: '/blog/heyri/sub2.asp'},
            { title: '박물관.미술관', link: '/blog/heyri/sub2_2.asp?searchstr=박물관'},
            { title: '갤러리', link: '/blog/heyri/sub2_1.asp?searchstr=갤러리'},
            { title: '공연', link: '/blog/heyri/sub2_1.asp?searchstr=공연'},
            { title: '전문강좌', link: '/blog/heyri/sub2_1.asp?searchstr=전문강좌'},
            { title: '체험', link: '/blog/heyri/sub2_1.asp?searchstr=체험'},
            { title: '상업전시공간', link: '/blog/heyri/sub2_1.asp?searchstr=상업전시공간'},
            { title: '카페', link: '/blog/heyri/sub2_1.asp?searchstr=카페'},
            { title: '레스토랑', link: '/blog/heyri/sub2_1.asp?searchstr=레스토랑'},
            { title: '회원관련시설', link: '/blog/heyri/sub2_1.asp?searchstr=회원관련시설'},
            { title: '공지사항', link: '/blog/board/n_list.asp'},
            { title: '헤이리데일리뉴스', link: '/blog/board/dailynews_list.asp'}]
          },{
            title: '헤이리블로그',
            tabs: [
              { title: '블로그전체목록', link: '/blog/main/main.asp'},
              { title: '최신포스팅보기', link: '/blog/main/new_post.asp'}]
          },{
            title: '헤이리공간',
            tabs: [
              { title: '갤러리', link: '/blog/board/sub5_list.asp?searchstr=갤러리'},
              { title: '박물관', link: '/blog/board/sub5_list.asp?searchstr=박물관'},
              { title: '공연/소극장', link: '/blog/board/sub5_list.asp?searchstr=소극장'},
              { title: '아트샵', link: '/blog/board/sub5_list.asp?searchstr=아트샵'},
              { title: '서점', link: '/blog/board/sub5_list.asp?searchstr=서점'},
              { title: '공간대관', link: '/blog/board/sub5_list.asp?searchstr=워크숍'},
              { title: '레스토랑', link: '/blog/board/sub5_list.asp?searchstr=레스토랑'},
              { title: '카페', link: '/blog/board/sub5_list.asp?searchstr=카페'},
              { title: '오픈작가공방', link: '/blog/board/sub5_list.asp?searchstr=오픈공간'}]
          },{
            title: '커뮤니티',
            tabs: [
              { title: '질문관 답변', link: '/blog/board/b7_list.asp'},
              { title: '자주묻는질문', link: '/blog/heyri/sub7_1.asp'},
              { title: '자유게시판', link: '/blog/board/b6_list.asp'}]
          }
        ]
    }
  },
  methods: {
    tabBtn: function(e) {
      window.location.href = e.link
    }
  },
  computed: {
    whichTab: function() {
      const active = parseInt(this.active)
      const url = location.pathname
      if( url.includes('sub1') ){
        return '0'
      }else if ( url.includes('sub2') | url.includes('dailynews')){
        return '1'
      }else if ( url.includes('sub3') | url.includes('blog/main/main.asp')| url.includes('new_post')){
        return '2'
      }else if ( url.includes('sub5_list')){
        return '3'
      }else if ( url.includes('b7_list') |url.includes('b6_list') |url.includes('sub7')){
        return '4'
      }
    }
  }
}
</script>
<style scoped>
/* @import url(http://fonts.googleapis.com/earlyaccess/nanumgothic.css);
* {
  font-family: 'Nanum Gothic', serif;
  font-size: 1.02em;
  font-weight: 600;
} */
 #edit-1 {
   flex: 1 1;
 }
</style>
