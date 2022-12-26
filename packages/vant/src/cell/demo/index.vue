<script setup lang="ts">
import VanCellGroup from '../../cell-group';
import VanCell from '..';
import VanTag from '../../tag';
import VanIcon from '../../icon';
import { useTranslate } from '../../../docs/site';

const t = useTranslate({
  'zh-CN': {
    cell: '单元格',
    group: '分组',
    router: '页面导航',
    urlRoute: 'URL 跳转',
    vueRoute: '路由跳转',
    useSlots: '使用插槽',
    showIcon: '展示图标',
    showArrow: '展示箭头',
    largeSize: '单元格大小',
    groupTitle: '分组标题',
    insetGrouped: '卡片风格',
    verticalCenter: '垂直居中',
    fullWidthContent: '全宽内容',
    longContent:
      '子言慕雨，啟傘避之。子言好陽，尋蔭拒之。子言喜風，闔戶離之。子言偕老，吾所畏之。',
  },
  'en-US': {
    cell: 'Cell title',
    group: 'Group',
    router: 'Router',
    urlRoute: 'URL',
    vueRoute: 'Vue Router',
    useSlots: 'Use Slots',
    showIcon: 'Left Icon',
    showArrow: 'Link',
    largeSize: 'Size',
    groupTitle: 'Group Title',
    insetGrouped: 'Inset Grouped',
    verticalCenter: 'Vertical center',
    fullWidthContent: 'Full Width Content',
    longContent:
      'You say that you love rain, but you open your umbrella when it rains. You say that you love the sun, but you find a shadow spot when the sun shines. You say that you love the wind, but you close your windows when wind blows. This is why I am afraid, you say that you love me too.',
  },
});
</script>

<template>
  <demo-block :title="t('basicUsage')">
    <van-cell-group>
      <van-cell :title="t('cell')" :value="t('content')" />
      <van-cell :title="t('cell')" :value="t('content')" :label="t('desc')" />
    </van-cell-group>
  </demo-block>

  <demo-block :title="t('insetGrouped')">
    <van-cell-group inset>
      <van-cell :title="t('cell')" :value="t('content')" />
      <van-cell :title="t('cell')" :value="t('content')" :label="t('desc')" />
    </van-cell-group>
  </demo-block>

  <demo-block :title="t('largeSize')">
    <van-cell :title="t('cell')" :value="t('content')" size="large" />
    <van-cell
      :title="t('cell')"
      :value="t('content')"
      size="large"
      :label="t('desc')"
    />
  </demo-block>

  <demo-block :title="t('showIcon')">
    <van-cell :title="t('cell')" :value="t('content')" icon="location-o" />
  </demo-block>

  <demo-block :title="t('showArrow')">
    <van-cell :title="t('cell')" is-link />
    <van-cell :title="t('cell')" is-link :value="t('content')" />
    <van-cell
      :title="t('cell')"
      is-link
      arrow-direction="down"
      :value="t('content')"
    />
  </demo-block>

  <demo-block :title="t('router')">
    <van-cell
      :title="t('urlRoute')"
      is-link
      url="https://github.com/vant-ui/vant"
    />
    <van-cell :title="t('vueRoute')" is-link to="index" />
  </demo-block>

  <demo-block :title="t('groupTitle')">
    <van-cell-group :title="`${t('group')} 1`">
      <van-cell :title="t('cell')" :value="t('content')" />
    </van-cell-group>
    <van-cell-group :title="`${t('group')} 2`">
      <van-cell :title="t('cell')" :value="t('content')" />
    </van-cell-group>
  </demo-block>

  <demo-block :title="t('useSlots')">
    <van-cell :value="t('content')" is-link>
      <template #title>
        <span class="custom-title">{{ t('cell') }}</span>
        <van-tag type="primary">{{ t('tag') }}</van-tag>
      </template>
    </van-cell>

    <van-cell icon="shop-o" :title="t('cell')">
      <template #right-icon>
        <van-icon name="search" class="search-icon" />
      </template>
    </van-cell>

    <van-cell :title="t('cell')" :value="t('content')">
      <template #content>
        {{ t('longContent') }}
      </template>
    </van-cell>
  </demo-block>

  <demo-block :title="t('verticalCenter')">
    <van-cell
      center
      :title="t('cell')"
      :value="t('content')"
      :label="t('desc')"
    />
  </demo-block>
</template>

<style lang="less">
.demo-cell {
  .custom-title {
    margin-right: 4px;
    vertical-align: middle;
  }

  .search-icon {
    font-size: 16px;
    line-height: inherit;
  }
}
</style>
