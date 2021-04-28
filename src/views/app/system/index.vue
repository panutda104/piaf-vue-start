<template>
<div>
 <div class="col-12">
      <div class="mb-2">
        <h1>วันหมดอายุการใช้งานระบบ</h1>
      </div>
    </div>
    <div class="separator mb-5"></div>
 
  <!-- <b-row>
    <b-colxx xxs="12">
      <piaf-breadcrumb :heading="$t('menu.system')"/>
      <div class="separator mb-5"></div>
    </b-colxx>
  </b-row>
  <b-row>
    <b-colxx xxs="12">
        <b-card class="mb-4" :title="$t('menu.system')" >
        </b-card>
    </b-colxx>
  </b-row> -->

  <div>
    <b-modal id="modal-1" ref="my-modal" title="แก้ไขวันหมดอายุระบบ">
        <div class="form-group row">
          <label for="domain"  class="col-sm-3 col-form-label">Domain:</label>
          <div class="col-sm-8">
              <input type="text" class="form-control"  v-model="dataedit.domain"  id="domain">
          </div>
      </div>


    <div class="form-group row">
          <label for="namecustomer" class="col-sm-3 col-form-label">ชื่อร้าน:</label>
          <div class="col-sm-8">
              <input type="text" class="form-control"  v-model="cmzsubdomain.domain" id="namecustomer">
          </div>
      </div>
      
      <div class="form-group row">
          <label for="tel" class="col-sm-3 col-form-label">เบอร์โทรศัพท์:</label>
          <div class="col-sm-8">
              <input type="text" class="form-control"  v-model="phone.domain" id="tel">
          </div>
      </div>


     <div class="form-group row">
          <label for="package" class="col-sm-3 col-form-label">วันหมดอายุ:</label>
          <div class="col-sm-8">
              <b-form-datepicker 
                id="susdate" v-model="lastupdatestoc.domain"
                class="mb-2"
              ></b-form-datepicker>
          </div>
      </div>
      
      <div class="form-group row">
          <label for="package" class="col-sm-3 col-form-label">เพคเกจ:</label>
          <div class="col-sm-8">
             <select class="form-control" style="height: auto;"  v-model="package.domain"> 
            <option value="-">-</option>
            <option value="B">B</option>
            <option value="D">D</option>
            <option value="A">A</option>
          </optgroup>
        </select>
          </div>
      </div>
 
    <div class="form-group row">
        <label for="page" class="col-sm-3 col-form-label">จำนวนเพจ:</label>
        <div class="col-sm-8">
            <input type="text"  disable="disable" class="form-control"   v-model="chat.domain" id="page"  >
        </div>
      </div>

      <div class="form-group row">
          <label for="version" class="col-sm-3 col-form-label">เวอร์ชั่น:</label>
          <div class="col-sm-8">
              <input type="text"  disable="disable" class="form-control"  v-model="version.domain" id="version"  >
          </div>
      </div>

       <div class="form-group row">
                <label for="dropship" class="col-sm-3 col-form-label">dropship:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control"  v-model="dropship.domain" id="dropship"  >
                </div>
              </div>

            <div class="form-group row">
                <label for="ecommerce" class="col-sm-3 col-form-label">ecommerce:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control" v-model="ecommerce.domain" id="ecommerce"  >
                </div>
              </div>
              
              <div class="form-group row">
                <label for="affiliate" class="col-sm-3 col-form-label">affiliate:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control" v-model="affiliate.domain" id="affiliate"  >
                </div>
              </div>

            
              <div class="form-group row">
                <label for="mlm" class="col-sm-3 col-form-label">mlm:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control"   v-model="mlm.domain" id="mlm"  >
                </div>
              </div>

            <div class="form-group row">
                <label for="pos" class="col-sm-3 col-form-label">pos:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control" v-model="pos.domain" id="pos"  >
                </div>
              </div>

          
             <div class="form-group row">
                <label for="linebroadcast" class="col-sm-3 col-form-label">line broadcast:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control" v-model="linebroadcast.domain"  id="linebroadcast"  >
                </div>
              </div>

             <div class="form-group row">
                <label for="marketplace" class="col-sm-3 col-form-label">number marketplace:</label>
                <div class="col-sm-8">
                    <input type="text"  disable="disable" class="form-control" v-model="numbermarketplace.domain" id="marketplace"  >
                </div>
              </div>

    </b-modal>
  </div>

   <div class="col-12">
   <div class="card">
      <div class="card-body">
        <b-input v-model="searchQuery"
        type="text"class="form-control" style="width: 50%;margin-bottom: 2%;border-radius: 15px;"placeholder="ค้นหา  Domain หรือ ชื่อร้าน "
        ></b-input>
        
      <table class="table">
            <thead class="thead-light">
              <tr>
                <th scope="col">Site ID</th>
                <th scope="col">Domain</th>
                <th scope="col">Package</th>
                <th scope="col">วันหมดอายุ</th>
                <th scope="col">ชื่อร้าน</th>
                <th scope="col">เวอร์ชั่น</th>
                <th scope="col-1"></th>
                 <th scope="col-1"></th>
              </tr>
            </thead>
            
            <tbody>
            <!-- v-for="item in items" :key="item.site_id" -->
              <tr v-for="item in resultQuery" :key="item.site_id" >
                <!-- <th scope="row">1</th> -->
                <td>{{ item.site_id }}</td>
                <td>{{ item.main_app_domain}}</td>
                <td >{{ item.package }}</td>
                <td>{{ item.last_update_stock_value }}</td>
                <td>{{ item.cmz_subdomain }}</td>
                <td>{{ item.crm_version }}</td>
               
                <td><div class="mb-4">                              
                    <b-button  @click="editdata(item)" >Edit</b-button>                  
                 </div></td>          
              </tr>
              
            </tbody>
          </table>

        <div class="top-right-button-container">
              <div class="modal fade bd-example-modal-lg" tabindex="-1" role="dialog" aria-hidden="true">
                <div class="modal-dialog modal-lg">
                <div class="modal-content">                                
                </div>
            </div>
            </div> 
            </div>
        </div>
      </div>
    </div> 
    </div>
    
  </div>
</template>

<script>
export default {
  // data () {
  //   return {
  //     selectedBackdrop: 'true',
  //     backdropOptions: ['true', 'false', 'static']
  //   }
  // },
  
  methods: {
    hideModal (refname) {
      this.$refs[refname].hide()
      console.log('hide modal:: ' + refname)

      if (refname === 'modalnestedinline') {
        this.$refs['modalnested'].show()
      }
    },
    somethingModal (refname) {
      this.$refs[refname].hide()
      console.log('something modal:: ' + refname)

      if (refname === 'modalnestedinline') {
        this.$refs['modalnested'].show()
      }
    }
  }
}

</script>
<script>
import datasite from "C:/Users/User/Desktop/piaf-vue-start/src/data/noti";

export default {
  name: "domain",
  data() {
    return {
      searchQuery:null,
      items: datasite, 
      dataedit:{
        domain:null,
        cmzsubdomain:null
      },
      cmzsubdomain:{
        cmzsubdomain:null
      },
      lastupdatestoc:{
        lastupdatestoc:null
      },
      package:{
        package:null
      },
      chat:{
        chat: null
      },
      version:{
        version:null
      },
      dropship:{
        dropship:null
      },
      ecommerce:{
        ecommerce:null
      },
      affiliate:{
        affiliate:null
      },
      mlm:{
        mlm: null
      },
      phone:{
        phone:null
      },
      pos:{
        pos:null
      },
      linebroadcast:{
        linebroadcast:null
      },
      numbermarketplace:{
        numbermarketplace:null
      }
    };
  },
  methods:{
editdata(item){

  this.dataedit.domain=item.main_app_domain;
  console.log("test",this.dataedit.domain,item.main_app_domain)

  this.cmzsubdomain.domain=item.cmz_subdomain;
  console.log("test",this.cmzsubdomain.domain,item.cmz_subdomain)

  this.lastupdatestoc.domain=item.last_update_stock_value;
  console.log("test",this.lastupdatestoc.domain,item.last_update_stock_value)

  this.package.domain=item.package;
  console.log("test",this.package.domain,item.package)

  this.chat.domain=item.chat;
  console.log("test",this.chat.domain,item.chat)

  this.version.domain=item.crm_version;
  console.log("test",this.version.domain,item.crm_version)

  this.dropship.domain=item.dropship;
  console.log("test",this.dropship.domain,item.dropship)

  this.ecommerce.domain=item.ecommerce;
  console.log("test",this.ecommerce.domain,item.ecommerce)

  this.affiliate.domain=item.affiliate;
  console.log("test",this.affiliate.domain,item.affiliate)

  this.mlm.domain=item.mlm;
  console.log("test",this.affiliate.domain,item.mlm)

  this.phone.domain=item.phone;
  console.log("test",this.phone.domain,item.phone)

  this.pos.domain=item.pos;
  console.log("test",this.pos.domain,item.pos)

  this.linebroadcast.domain=item.line_broadcast;
  console.log("test",this.linebroadcast.domain,item.line_broadcast)

  this.numbermarketplace.domain=item.number_marketplace;
  console.log("test",this.numbermarketplace.domain,item.number_marketplace)

  this.$refs['my-modal'].show()
}

  },
  
//  methods:{
//   editdata(item){

//   this.dataedit.cmzsubdomain=item.cmz_subdomain;
//   console.log("test",this.dataedit.cmzsubdomain,item.cmz_subdomain)
//   this.$refs['my-modal'].show()
// }
//   },
  

   computed: {  
      resultQuery(){
        var self = this;
      if(this.searchQuery){
      return this.items.filter((item)=>{
        return item.main_app_domain.toLowerCase().indexOf(self.searchQuery.toLowerCase()) >= 0
                || item.cmz_subdomain.toLowerCase().indexOf(self.searchQuery.toLowerCase()) >= 0;
         
     //  return this.searchQuery.toLowerCase().split(' ').every(v => item.cmz_subdomain.toLowerCase().includes(v) )
      })
      }else{
        return this.items;
      }
    }
 },
 
};
</script>
