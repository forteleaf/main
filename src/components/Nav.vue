<template>
  <v-container>
    <v-tabs>
      <img src="@/assets/logo_red_korean.png" alt="logo" height="100%">
      <v-spacer></v-spacer>
      <v-tab
      v-for="(item, index) in items"
      :key="index">
      {{item.title}}
      </v-tab>
    </v-tabs>
    <!-- <v-toolbar dense class="elevation-0">
      <img src="@/assets/logo_red_korean.png" alt="logo" height="100%">
      <v-spacer></v-spacer>
      <v-toolbar-items
      v-for="(item, index) in items"
      :key="index">
        <v-menu open-on-hover absolute :nudge-bottom="50" data-app="this">
          <v-btn flat slot="activator" class="portrait">{{item.title}}</v-btn>
          <v-list>
            <v-list-tile v-for="(tab, i) in item.tabs" :key="i" @click="tabBtn(tab)">
              <v-list-tile-title>{{tab.title}}</v-list-tile-title>
            </v-list-tile>
          </v-list>
        </v-menu>
      </v-toolbar-items>
    </v-toolbar> -->
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      show: false,
      active: null,
      showMenu: false,
      items: [
        {
          'title': '헤이리소개',
          'tabs': [
            { 'title': '헤이리개요','link': '/blog/heyri/sub1.asp'},
            { 'title': '헤이리조직도','link': '/blog/heyri/sub1_1.asp'},
            { 'title': '휴-벨트 프로젝트','link': '/blog/heyri/sub1_7.asp'},
            { 'title': '제휴 및 후원안내','link': '/blog/heyri/sub1_3.asp'},
            { 'title': '헤이리촬영안내','link': '/blog/heyri/sub1_4.asp'},
            { 'title': '월요일오픈공간안내','link': '/blog/heyri/sub1_5.asp'},
            { 'title': '찾아오시는길','link': '/heyri/sub1_6.asp'}]
        },{
          'title': '헤이리소식',
          'tabs': [
            { 'title': '헤이리소식','link': '/blog/heyri/sub2.asp'},
            { 'title': '박물관.미술관','link': '/blog/heyri/sub2_2.asp?searchstr=박물관'},
            { 'title': '갤러리','link': '/heyri/sub2_1.asp?searchstr=갤러리'},
            { 'title': '공연','link': '/blog/heyri/sub2_1.asp?searchstr=공연'},
            { 'title': '전문강좌','link': '/blog/heyri/sub2_1.asp?searchstr=전문강좌'},
            { 'title': '체험','link': '/blog/heyri/sub2_1.asp?searchstr=체험'},
            { 'title': '상업전시공간','link': '/blog/heyri/sub2_1.asp?searchstr=상업전시공간'},
            { 'title': '카페','link': '/blog/heyri/sub2_1.asp?searchstr=카페'},
            { 'title': '레스토랑','link': '/blog/heyri/sub2_1.asp?searchstr=레스토랑'},
            { 'title': '회원관련시설','link': '/blog/heyri/sub2_1.asp?searchstr=회원관련시설'},
            { 'title': '공지사항','link': '/blog/board/n_list.asp'},
            { 'title': '헤이리데일리뉴스','link': '/blog/board/dailynews_list.asp'}]
          },{
            'title': '헤이리블로그',
            'tabs': [
              { 'title': '블로그전체목록','link': '/blog/main/main.asp'},
              { 'title': '최신포스팅보기','link': '/blog/main/new_post.asp'}]
          },{
            'title': '헤이리공간',
            'tabs': [
              { 'title': '갤러리','link': '/blog/board/sub5_list.asp?searchstr=갤러리'},
              { 'title': '박물관','link': '/blog/board/sub5_list.asp?searchstr=박물관'},
              { 'title': '공연/소극장','link': '/blog/board/sub5_list.asp?searchstr=소극장'},
              { 'title': '아트샵','link': '/blog/board/sub5_list.asp?searchstr=아트샵'},
              { 'title': '서점','link': '/blog/board/sub5_list.asp?searchstr=서점'},
              { 'title': '공간대관','link': '/blog/board/sub5_list.asp?searchstr=워크숍'},
              { 'title': '레스토랑','link': '/blog/board/sub5_list.asp?searchstr=레스토랑'},
              { 'title': '카페','link': '/blog/board/sub5_list.asp?searchstr=카페'},
              { 'title': '오픈작가공방','link': '/blog/board/sub5_list.asp?searchstr=오픈공간'}]
          },{
            'title': '커뮤니티',
            'tabs': [
              { 'title': '질문관 답변','link': '/blog/board/b7_list.asp'},
              { 'title': '자주묻는질문','link': '/blog/heyri/sub7_1.asp'},
              { 'title': '자유게시판','link': '/blog/board/b6_list.asp'}]
          },{
            'title': '헤이리지도',
            'link': ''
          }
        ],
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
    }
  },
  methods: {
    tabBtn(e) {
      window.location.href = e.link
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
</style>
