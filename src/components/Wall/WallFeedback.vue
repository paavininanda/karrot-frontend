<template>
  <!-- unused component; remove? -->
  <div>
    <template slot="icon">
      <div class="icon">
        <i class="fa fa-shopping-cart"/>
      </div>
    </template>
    <template slot="header">
      <div>
        <ProfilePicture :user="feedback.givenBy" />
      </div>
      <div>picked up food</div>
    </template>
    <template slot="time">
      {{ $d(feedback.createdAt, 'long') }}
    </template>
    <AmountBox :amount="feedback.weight"/>
    <div class="comment"> {{ feedback.comment }} </div>
  </div>
</template>

<script>
import AmountBox from '@/components/Statistics/AmountBox'
import ProfilePicture from '@/components/ProfilePictures/ProfilePicture'

export default {
  components: {
    ProfilePicture, AmountBox,
  },
  props: {
    feedback: { required: true, type: Object },
  },
}
</script>

<style scoped lang="stylus">
@import '~variables'

.icon
  height 32px
  width 32px
  background-color $primary
  color $tertiary
  .fa
    line-height 32px
    vertical-align middle
    text-align center
    margin-left 10px
.header div
  display inline-block
  vertical-align middle
.comment
  display inline-block
  vertical-align middle
  margin-left .6em
</style>
