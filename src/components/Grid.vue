<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>

    <table id="example" class="display" cellspacing="0" width="100%"></table>
  </div>
</template>

<script>
// import axios from "axios";

//https://yaruzou.net/js-datatables-b3
//https://qiita.com/nissuk/items/7ac59af5de427c0585c5
//https://m.datatables.net/reference/api/
//https://datatables.net/reference/option/infoCallback
export default {
  name: "HelloWorld",
  data() {
    return {
      msg: 'Welcome to Your Vue.js App2222',
      info: null
    };
  },
  mounted() {
    console.log("mounted");


    var columns = [
      {
        title: "",
        target: 0,
        className: "treegrid-control",
        data: function(item) {
          if (item.children) {
            // return "&ltspan&gt++&lt/span&gt";

            return "<span>+</span>";

          }
          return "";
        }
      },
      {
        title: "Name",
        target: 1,
        data: function(item) {
          return item.name;
        }
      },
      {
        title: "Position",
        target: 2,
        data: function(item) {
          return item.position;
        }
      },
      {
        title: "Office",
        target: 3,
        data: function(item) {

return "<a id='edit' href='javascript:void(0)'>リンク1</a>"
          // return item.office;
        }
      },
      // // {
      // //   title: "Extn.",
      // //   target: 4,
      // //   data: function(item) {
      // //     return item.extn;
      // //   }
      // // },
      // // {
      // //   title: "Start date",
      // //   target: 5,
      // //   data: function(item) {
      // //     return item.start;
      // //   }
      // // },
      // // {
      // //   title: "Salary",
      // //   target: 6,
      // //   data: function(item) {
      // //     return item.salary;
      // //   }
      // }
    ];

    $("#example").DataTable({

paging: false,//デフォルトでtrueなので、なくてもOK
orderable: false,
scrollX: true,

        language: {
          sEmptyTable: 'テーブルにデータがありません',
          sInfo: ' _TOTAL_ 件中 _START_ から _END_ まで表示',
          sInfoEmpty: ' 0 件中 0 から 0 まで表示',
          sInfoFiltered: '（全 _MAX_ 件より抽出）',
          sInfoPostFix: '',
          sInfoThousands: ',',
          sLengthMenu: '_MENU_ 件表示',
          sLoadingRecords: '読み込み中...',
          sProcessing: '処理中...',
          sSearch: '検索:',
          bProcessing: true,
          sZeroRecords: '一致するレコードがありません',
          oPaginate: {
            sFirst: '先頭',
            sLast: '最終',
            sNext: '次へ',
            sPrevious: '前へ'
          },
        },


"columnDefs": [{ "orderable": false, "targets": 2 }],

      columns: columns,
      ajax: "/arrays",
      treeGrid: {
        left: 20,
        // expandIcon: "&lt;span&gt;+&lt;/span&gt;",
        // collapseIcon: "&lt;span&gt;-&lt;/span&gt;"

        expandIcon: "<span>+</span>",
        collapseIcon: "<span>-</span>"

      },



    });


      $('#example tbody').on('click', 'a#edit', function () {

console.info("edit");


      })



    // axios.post('/auth/login').then(response => (this.info = response))
  }
};
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
