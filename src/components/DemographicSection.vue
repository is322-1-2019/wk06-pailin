<template>
<div>
  <form>
    <div class="form-row">
      <div class="form-group col-md-2">
        <label for="prefix">Prefix</label>
        <select id="prefix" class="form-control" v-model="demoInfo.prefix">
          <option selected>Not specified</option>
          <option>Mr</option>
          <option>Mrs</option>
          <option>Miss</option>
        </select>
      </div>
      <div class="form-group col-md-5">
        <label for="firstName">FirstName</label>
        <input type="text" v-model="demoInfo.firstName" class="form-control" id="firstName" placeholder="FirstName" />
      </div>
      <div class="form-group col-md-5">
        <label for="lastName">LastName</label>
        <input type="text" v-model="demoInfo.lastName" class="form-control" id="lastName" placeholder="LastName" />
      </div>
    </div>
    <div class="form-row">
      <div class="form-group col-md-2">
        <label for="sex">Sex</label>
        <select  v-model="demoInfo.sex" id="sex" class="form-control">
          <option selected>Not specified</option>
          <option>Male</option>
          <option>Female</option>
        </select>
      </div>
      <div class="form-group col-md-2">
        <label for="age">Age</label>
        <select  v-model="demoInfo.age" id="age" class="form-control">
          <option selected>Choose...</option>
          <option v-for="age in ageList"
            v-bind:key="age"
            v-bind:value="age"
            >{{ age }}</option>
        </select>
      </div>
      <div class="form-group col-md-8">
        <label for="occupation">Occupation</label>
        <input type="text" v-model="demoInfo.occupation" class="form-control" id="occupation" placeholder="Occupation" />
      </div>
    </div>
    <div class="form-group">
      <label for="address">Address</label>
      <input type="text" v-model="demoInfo.address" class="form-control" id="address" placeholder="1234 Main St" />
    </div>
    <div class="form-row">
      <div class="form-group col-md-6">
        <label for="district">District</label>
        <input type="text" v-model="demoInfo.district" class="form-control" id="district" />
      </div>
      <div class="form-group col-md-4">
        <label for="city">City</label>
        <select  v-model="demoInfo.city" id="city" class="form-control">
          <option selected>Choose...</option>
          <option v-for="city in cityList"
            v-bind:key="city.id"
            v-bind:value="city.name"
          >{{ city.name }}</option>
        </select>
      </div>
      <div class="form-group col-md-2">
        <label for="postcode">Postcode</label>
        <input type="text" v-model="demoInfo.postcode" class="form-control" id="postcode" />
      </div>
    </div>
  </form>
  <p> {{ demoInfo }} </p>
</div>
</template>

<script>
export default {
  data() {
    return {
      demoInfo : {
        prefix : '',
        firstName : '',
        lastName : '',
        sex : '',
        age : 1,
        address : '',
        district : '',
        city : '',
        postcode : '',
      },
      maxAge : 100,
      cityList: [
        {id: 1, name: "Amnat Charoen"},
        {id: 2, name: "Ang Thong"},
        {id: 3, name: "Bangkok"},
        {id: 4, name: "Bueng Kan"},
        {id: 5, name: "Buriram"},
        {id: 5, name: "Chachoengsao"},
        {id: 6, name: "Chai Nat"},
        {id: 7, name: "Chaiyaphum"},
        {id: 8, name: "Chanthaburi"},
        {id: 9, name: "Chiang Mai"},
        {id: 10, name: "Chiang Rai"},
        {id: 11, name: "Chonburi"},
        {id: 12, name: "Chumphon"},
        {id: 13, name: "Kalasin"},
        {id: 14, name: "Kamphaeng Phet"},
        {id: 15, name: "Kanchanaburi"},
        {id: 16, name: "Khon Kaen"},
        {id: 17, name: "Krabi"},
        {id: 18, name: "Lampang"},
        {id: 19, name: "Lamphun"},
        {id: 20, name: "Loei"},
        {id: 21, name: "Lopburi"},
        {id: 22, name: "Mae Hong Son"},
        {id: 23, name: "Maha Sarakham"},
        {id: 24, name: "Mukdahan"},
        {id: 25, name: "Nakhon Nayok"},
        {id: 26, name: "Nakhon Pathom"},
        {id: 27, name: "Nakhon Phanom"},
        {id: 28, name: "Nakhon Ratchasima"},
        {id: 29, name: "Nakhon Sawan"},
        {id: 30, name: "Nakhon Si Thammarat"},
        {id: 31, name: "Nan"},
        {id: 32, name: "Narathiwat"},
        {id: 33, name: "Nong Bua Lamphu"},
        {id: 34, name: "Nong Khai"},
        {id: 35, name: "Nonthaburi"},
        {id: 36, name: "Pathum Thani"},
        {id: 37, name: "Pattani"},
        {id: 38, name: "Phang Nga"},
        {id: 39, name: "Phatthalung"},
        {id: 40, name: "Phayao"},
        {id: 41, name: "Phetchabun"},
        {id: 42, name: "Phetchaburi"},
        {id: 43, name: "Phichit"},
        {id: 44, name: "Phitsanulok"},
        {id: 45, name: "Phra Nakhon Si Ayutthaya"},
        {id: 46, name: "Phrae"},
        {id: 47, name: "Phuket"},
        {id: 48, name: "Prachinburi"},
        {id: 49, name: "Prachuap Khiri Khan"},
        {id: 50, name: "Ranong"},
        {id: 51, name: "Ratchaburi"},
        {id: 52, name: "Rayong"},
        {id: 53, name: "Roi Et"},
        {id: 54, name: "Sa Kaeo"},
        {id: 55, name: "Sakon Nakhon"},
        {id: 56, name: "Samut Prakan"},
        {id: 57, name: "Samut Sakhon"},
        {id: 58, name: "Samut Songkhram"},
        {id: 59, name: "Saraburi"},
        {id: 60, name: "Satun"},
        {id: 61, name: "Sing Buri"},
        {id: 62, name: "Sisaket"},
        {id: 63, name: "Songkhla"},
        {id: 64, name: "Sukhothai"},
        {id: 65, name: "Suphan Buri"},
        {id: 66, name: "Surat Thani"},
        {id: 67, name: "Surin"},
        {id: 68, name: "Tak"},
        {id: 69, name: "Trang"},
        {id: 70, name: "Trat"},
        {id: 71, name: "Ubon Ratchathani"},
        {id: 72, name: "Udon Thani"},
        {id: 73, name: "Uthai Thani"},
        {id: 74, name: "Uttaradit"},
        {id: 75, name: "Yala"},
        {id: 76, name: "Yasothon"}
      ]
    };
  },
  computed: {
    ageList: function() {
        return Array(this.maxAge)
                .fill(null).map( (x,i) => i )
                .filter( (x) => x > 15);
    }
  }
};
</script>