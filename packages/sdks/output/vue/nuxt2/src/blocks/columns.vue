<template>
  <div class="builder-columns div-4op4jcgbkl">
    <div
      class="builder-column div-4op4jcgbkl-2"
      v-for="(column, index) in columns"
      :style="{
        width: getColumnCssWidth(index),
        marginLeft: `${index === 0 ? 0 : getGutterSize()}px`,
      }"
      :key="index"
    >
      <render-blocks :blocks="column.blocks"></render-blocks>
    </div>
  </div>
</template>
<script>
import RenderBlocks from '../components/render-blocks';

import { registerComponent } from '@builder.io/sdk-vue';

export default registerComponent(
  {
    name: 'builder-columns',
    components: { 'render-blocks': async () => RenderBlocks },
    props: ['space', 'columns'],

    methods: {
      getGutterSize() {
        return typeof this.space === 'number' ? this.space || 0 : 20;
      },
      getColumns() {
        return this.columns || [];
      },
      getWidth(index) {
        const columns = this.getColumns();
        return (columns[index] && columns[index].width) || 100 / columns.length;
      },
      getColumnCssWidth(index) {
        const columns = this.getColumns();
        const gutterSize = this.getGutterSize();
        const subtractWidth = (gutterSize * (columns.length - 1)) / columns.length;
        return `calc(${this.getWidth(index)}% - ${subtractWidth}px)`;
      },
    },
  },
  {
    name: 'Columns',
    builtIn: true,
    inputs: [
      {
        name: 'columns',
        type: 'array',
        broadcast: true,
        subFields: [
          {
            name: 'blocks',
            type: 'array',
            hideFromUI: true,
            defaultValue: [
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                    minHeight: '20px',
                    minWidth: '20px',
                    overflow: 'hidden',
                  },
                },
                component: {
                  name: 'Image',
                  options: {
                    image:
                      'https://builder.io/api/v1/image/assets%2Fpwgjf0RoYWbdnJSbpBAjXNRMe9F2%2Ffb27a7c790324294af8be1c35fe30f4d',
                    backgroundPosition: 'center',
                    backgroundSize: 'cover',
                    aspectRatio: 0.7004048582995948,
                  },
                },
              },
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                  },
                },
                component: {
                  name: 'Text',
                  options: { text: '<p>Enter some text...</p>' },
                },
              },
            ],
          },
          {
            name: 'width',
            type: 'number',
            hideFromUI: true,
            helperText: 'Width %, e.g. set to 50 to fill half of the space',
          },
          {
            name: 'link',
            type: 'url',
            helperText: 'Optionally set a url that clicking this column will link to',
          },
        ],
        defaultValue: [
          {
            blocks: [
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                    minHeight: '20px',
                    minWidth: '20px',
                    overflow: 'hidden',
                  },
                },
                component: {
                  name: 'Image',
                  options: {
                    image:
                      'https://builder.io/api/v1/image/assets%2Fpwgjf0RoYWbdnJSbpBAjXNRMe9F2%2Ffb27a7c790324294af8be1c35fe30f4d',
                    backgroundPosition: 'center',
                    backgroundSize: 'cover',
                    aspectRatio: 0.7004048582995948,
                  },
                },
              },
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                  },
                },
                component: {
                  name: 'Text',
                  options: { text: '<p>Enter some text...</p>' },
                },
              },
            ],
          },
          {
            blocks: [
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                    minHeight: '20px',
                    minWidth: '20px',
                    overflow: 'hidden',
                  },
                },
                component: {
                  name: 'Image',
                  options: {
                    image:
                      'https://builder.io/api/v1/image/assets%2Fpwgjf0RoYWbdnJSbpBAjXNRMe9F2%2Ffb27a7c790324294af8be1c35fe30f4d',
                    backgroundPosition: 'center',
                    backgroundSize: 'cover',
                    aspectRatio: 0.7004048582995948,
                  },
                },
              },
              {
                '@type': '@builder.io/sdk:Element',
                responsiveStyles: {
                  large: {
                    display: 'flex',
                    flexDirection: 'column',
                    alignItems: 'stretch',
                    flexShrink: '0',
                    position: 'relative',
                    marginTop: '30px',
                    textAlign: 'center',
                    lineHeight: 'normal',
                    height: 'auto',
                  },
                },
                component: {
                  name: 'Text',
                  options: { text: '<p>Enter some text...</p>' },
                },
              },
            ],
          },
        ],
        onChange:
          "        function clearWidths() {          columns.forEach(col => {            col.delete('width');          });        }        const columns = options.get('columns') as Array<map<string, any>>;        if (Array.isArray(columns)) {          const containsColumnWithWidth = !!columns.find(col => col.get('width'));          if (containsColumnWithWidth) {            const containsColumnWithoutWidth = !!columns.find(col => !col.get('width'));            if (containsColumnWithoutWidth) {              clearWidths();            } else {              const sumWidths = columns.reduce((memo, col) => {                return memo + col.get('width');              }, 0);              const widthsDontAddUp = sumWidths !== 100;              if (widthsDontAddUp) {                clearWidths();              }            }          }        }      ",
      },
      {
        name: 'space',
        type: 'number',
        defaultValue: 20,
        helperText: 'Size of gap between columns',
        advanced: true,
      },
      {
        name: 'stackColumnsAt',
        type: 'string',
        defaultValue: 'tablet',
        helperText: 'Convert horizontal columns to vertical at what device size',
        enum: ['tablet', 'mobile', 'never'],
        advanced: true,
      },
      {
        name: 'reverseColumnsWhenStacked',
        type: 'boolean',
        defaultValue: false,
        helperText: 'When stacking columns for mobile devices, reverse the ordering',
        advanced: true,
      },
    ],
  }
);
</script>
<style scoped>
.div-4op4jcgbkl {
  display: flex;
  align-items: stretch;
  line-height: normal;
}
.div-4op4jcgbkl-2 {
  flex-grow: 1;
}
</style>
