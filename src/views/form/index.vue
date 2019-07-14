<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="标题">
        <el-input v-model="form.title" />
      </el-form-item>
      <el-form-item label="地址">
        <el-input v-model="form.url" />
      </el-form-item>
      <el-form-item label="图片">
        <el-input v-model="form.pic" />
      </el-form-item>
      <el-form-item label="网站">
        <el-input v-model="form.site" />
      </el-form-item>
      <el-form-item label="类别">
        <el-select v-model="form.channel" placeholder="please select your zone">
          <el-option label="技术" value="cs" />
          <el-option label="玩乐" value="fun" />
          <el-option label="资讯" value="news" />
          <el-option label="财经" value="finance" />
          <el-option label="科技" value="tech" />
          <el-option label="行业" value="industry" />
          <el-option label="教育" value="education" />
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">提交</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
import request from '@/utils/request'
export default {
  data() {
    return {
      form: {
        title: '',
        url: '',
        pic: '',
        site: '',
        channel: ''
      }
    }
  },
  methods: {
    onSubmit() {
      request({
        url: '/news/add',
        method: 'get',
        params: { "title": this.form.title, "url": this.form.url,
          "pic": this.form.pic, "site": this.form.site, "channel": this.form.channel }
      })
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
</style>

