<template>
  <div class="card">
    <div>
      <div class="explorer-inf">
        <form>
          <!-- class="explorerInf" -->
          <fieldset class="explorer-interval">
            <span style="display: block;text-align: center;color: rgb(7, 65, 133);">调查员信息</span><br>
          </fieldset>
          <fieldset class="explorer-interval">
            <span class="element-interval">姓名: </span><input type="text" name="name" style="width: 9rem;"><br>
          </fieldset>
          <fieldset class="explorer-interval">
            <span class="element-interval">玩家: </span><input type="text" name="playername" style="width: 9rem;"><span class="element-interval">时代：</span><input type="text" name="time"  style="width: 9rem;"><span>   </span>
          </fieldset>
          <fieldset class="explorer-interval">
            <span class="element-interval">职业: </span><input type="text" name="occupation" style="width: 9rem;"><br>
          </fieldset>
          <fieldset class="explorer-interval">
             <span class="element-interval">年龄: </span><input type="text" name="age" style="width: 9rem;">
          </fieldset>
          <fieldset class="explorer-interval">
             <span class="element-interval">性别: </span><select style="width: 9rem;margin-left: 0rem">
                  <option value="1">男</option>
                  <option value="2">女</option>
                </select><br>
          </fieldset>
          <fieldset class="explorer-interval">
             <span class="element-interval">住地: </span><input type="text" name="habitation" style="width: 9rem;"><br>
          </fieldset>
          <fieldset class="explorer-interval">
             <span class="element-interval">故乡: </span><input type="text" name="hometown" style="width: 9rem;"><br>
          </fieldset>
          <!-- <input type="submit" value="提交"> -->
        </form>
      </div>
      <div class="quality">
        <form>
          <fieldset class="quality-interval">
            <span style="display: block;text-align: center;color: rgb(7, 65, 133);">属性</span><br>
          </fieldset>
          <fieldset class="quality-interval">
            <!-- (STR)(DEX)(STR)(CON)(APP)(EDU)(SIZ)(INT)(MOVE) -->
            <span class="element-interval">力量</span><input type="text" name="strength" style="width: 2.5rem;">
            <span class="element-interval">敏捷</span><input type="text" name="dexterity" style="width: 2.5rem;">
            <span class="element-interval">意志</span><input type="text" name="power" style="width: 2.5rem;">
          </fieldset>
          <fieldset class="quality-interval">
            <span class="element-interval">体质</span><input type="text" name="constitution" style="width: 2.5rem;">
            <span class="element-interval">外貌</span><input type="text" name="appearance" style="width: 2.5rem;">
            <span class="element-interval">教育</span><input type="text" name="education" style="width: 2.5rem;">
          </fieldset>
          <fieldset class="quality-interval">
            <span class="element-interval">体型</span><input type="text" name="size" style="width: 2.5rem;">
            <span class="element-interval">智力</span><input type="text" name="intelligence" style="width: 2.5rem;">
            <span class="element-interval">移动</span><input type="text" name="move" style="width: 2.5rem;">
          </fieldset>
          <!-- <fieldset>
             <span class="element-interval">年龄: </span><input type="text" name="age">
          </fieldset> -->
        </form>
        <div class="portrait">
          头像
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
  .card{
    margin: 0;
  }
  .explorer-inf{
    margin-top: 2rem;
    display: flex;
    margin-left: 3rem;
    
    float: left;
    width: 40%;
  }
  .quality{
    margin-top: 2rem;
    display: flex;
    float: left;
    margin-left: 2rem;
    width: 40%;
  }
  .portrait{
    margin-left: 2rem;
    height: 8rem;
    width: 8rem;
    border:0.1rem solid rgb(17, 17, 17);
    text-align: center;
  }
  .element-interval{
    margin-left: 1rem;
    margin-right: 1rem;
    /* margin-top: 1rem; */
    color: rgb(10, 136, 209);
  }
  .explorer-interval{
    color: rgb(10, 136, 209);
    height: 2rem;
    padding-right: 1rem;
  }
  .quality-interval{
    padding-top: 1rem;
    height: 4rem;
    padding-right: 1rem;
  }
</style>