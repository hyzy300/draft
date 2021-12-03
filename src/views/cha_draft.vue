<template>
  <!-- <div style="margin-top: 2rem;">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="姓名" style="width: 400px;" >
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="玩家" style="width: 200px;display: inline-block;margin-left: 60px;">
        <el-input v-model="form.player"></el-input>
      </el-form-item>
      <el-form-item label="Activity zone">
        <el-select v-model="form.region" placeholder="please select your zone">
          <el-option label="Zone one" value="shanghai"></el-option>
          <el-option label="Zone two" value="beijing"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="Activity time">
        <el-col :span="11">
          <el-date-picker
            v-model="form.date1"
            type="date"
            placeholder="Pick a date"
            style="width: 100%"
          ></el-date-picker>
        </el-col>
        <el-col class="line" :span="2">-</el-col>
        <el-col :span="11">
          <el-time-picker
            v-model="form.date2"
            placeholder="Pick a time"
            style="width: 100%"
          ></el-time-picker>
        </el-col>
      </el-form-item>
      <el-form-item label="Instant delivery">
        <el-switch v-model="form.delivery"></el-switch>
      </el-form-item>
      <el-form-item label="Activity type">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="Online activities" name="type"></el-checkbox>
          <el-checkbox label="Promotion activities" name="type"></el-checkbox>
          <el-checkbox label="Offline activities" name="type"></el-checkbox>
          <el-checkbox label="Simple brand exposure" name="type"></el-checkbox>
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="Resources">
        <el-radio-group v-model="form.resource">
          <el-radio label="Sponsor"></el-radio>
          <el-radio label="Venue"></el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="Activity form">
        <el-input v-model="form.desc" type="textarea"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Create</el-button>
        <el-button>Cancel</el-button>
      </el-form-item>
    </el-form>
  </div> -->
  <div class="message">
				  <div class="head-begin">
					<div class="head" style="text-align: center;border: 1px dashed #eeeeee;">
						<p id="touxiang">上传头像</p>
						<img id="imgtouxiang" style="display: table-cell;">
					</div>
					<div id="TCrop" style="z-index: 1; display: inline-block; border: 0px;"><iframe id="uploadIfr" name="uploadIfr" class="crop-hidden"></iframe><form action="./coc7/php/pic.php" enctype="multipart/form-data" method="post" target="uploadIfr"><input type="hidden" name="cropData" id="cropData"><div class="crop-picker-wrap"><button class="crop-picker" type="button">选择图片</button><input type="file" id="file" name="file" accept="image/jpg, image/jpeg, image/png, image/gif" class="crop-picker-file"></div><div class="crop-wrapper crop-hidden"><div class="crop-container"><div class="crop-area-wrapper"></div><div class="crop-preview-wrapper"><div class="crop-preview-container"></div></div></div><div class="crop-operate"><div class="crop-save">保存</div><div class="crop-cancel">取消</div></div></div></form></div>
				  </div>
					<div class="Content" style="border: 1px dashed #eeeeee;">
						<div style="height: 100%">
							<div class="Content-each-div" style="height: 10%">
							  <span class="Content-intucerod">姓名:</span>
							  <input type="text" id="chartname" style="width:437px;text-align: center;" value="">
							</div>
							<div class="Content-each-div" style="height: 10%">
							  <span class="Content-intucerod">玩家:</span>
							  <input type="text" id="player" style="width:190px;text-align: center;" value="">
						    </div>
							<div class="Content-each-div" style="height: 10%">
							<span class="Content-intucerod">時代:</span>
							<!--<input type="text" id="epoch" style="width:185px;text-align: center;" value="" />-->
							<select id="epoch" style="width:187px;height:21.36px;text-align: center;" onchange="setmoneytime(this.value)">
								<option value="1">1820~1920</option>
								<option value="2">1920~1990</option>
								<option value="3">1990~2010</option>
								<option value="4">2010~至今</option>
								<option value="5">文艺复兴时代</option>
								<option value="6">英国维多利亚时代</option>
								<option value="7">二战时期</option>
								<option value="8">中华民国时期</option>
								<option value="9">美苏冷战时期</option>
								<option value="10">大萧条(禁酒令)时期</option>
								<option value="11">嬉皮士时期</option>
								<option value="12">蒸汽朋克</option>
								<option value="13">架空历史</option>
								<option value="14">近未来</option>
								<option value="15">远未来</option>
								<option value="16">其他</option>
							</select>
						    </div>
							<div class="Content-each-div" style="height: 10%">
							  <span class="Content-intucerod">年龄:</span>
							  <input type="text" id="ages" style="width:190px;text-align: center;" value="">
						    </div>
							<div class="Content-each-div" style="height: 10%">
							<span class="Content-intucerod">性別:</span>
							<input type="text" id="sex" style="width:183px;text-align: center;" value="">
						    </div>
							<div class="Content-each-div" style="height: 10%">
							<span class="Content-intucerod">住地:</span>
							<input type="text" id="address" style="width:437px;text-align: center;" value="">
						    </div>
							<div class="Content-each-div" style="height: 10%">
							<span class="Content-intucerod">故乡:</span>
							<input type="text" id="hometown" style="width:437px;text-align: center;" value="">
						    </div>
						</div>
					</div>
				</div>
</template>

<script scope>
export default {
  data() {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: '',
      },
    }
  },
  methods: {
    onSubmit() {
      console.log('submit!')
    },
  },
}
</script>

<style>
.message {
    border: none;
    position: relative;
    display: flex;
    align-items: center;
}
  .head-begin {
      display: none;
  }

  .Content {
      margin: 15px;
      padding: 15px;
      width: 100%;
  }

  .Content-each-div {
      margin-top: 15px;
  }

  .Content-each-div input {
      width: 100% !important;
      color: #ffffff;
      height: 30px;
      border-radius: 6px;
      background-color: transparent;
      border: 1px solid #e0e0e0;
  }

  .Content-each-div select {
      width: 100% !important;
      height: 30px !important;
      border-radius: 6px;
      background-color: #f5f5f5;
      border: 1px solid #e0e0e0;
      /* color: #ffffff; */
      text-align-last: center;
  }

  .career {
      margin: 15px;
      padding: 15px;
      border: 1px dashed #eeeeee;
  }

  .career form {
      display: flex;
      flex-direction: column;
  }

  .career_label1 {
      margin: 0 0 0 10px !important;
      font-size: 18px;
      color: #ffffff;
      font-family: "Sim Sun";
      width: 100px;
  }

  .career_label2 {
      width: 100%;
      height: 30px !important;
      border-radius: 6px;
      background-color: #f5f5f5;
      border: 1px solid #e0e0e0;
      /* color: #bababa; */
      text-align-last: center;
  }

  #proskill {
      font-size: 18px;
      line-height: 20px;
      color: #ffffff;
      font-family: "Sim Sun";
  }
  .career span {
      width: 100%;
      display: inline-block;
  }

  .career_xypj {
      font-size: 18px;
      line-height: 20px;
      color: #ffffff;
  }

  .main1 {
      border: 1px dashed #eeeeee;
      margin: 15px;
      padding: 15px;
  }

  .left {
      margin-bottom: 20px;
      display: flex;
      justify-content: space-between;
  }

  .right {
      display: none;
      margin-top: 15px;
      background-color: #fff;
      border: none;
      margin-bottom: 20px;
  }
</style>