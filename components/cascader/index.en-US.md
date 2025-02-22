---
category: Components
type: Data Entry
title: Cascader
cover: https://gw.alipayobjects.com/zos/alicdn/UdS8y8xyZ/Cascader.svg
---

Cascade selection box.

## When To Use

- When you need to select from a set of associated data set. Such as province/city/district, company level, things classification.
- When selecting from a large data set, with multi-stage classification separated for easy selection.
- Chooses cascade items in one float layer for better user experience.

## API

```html
<a-cascader :options="options" v-model:value="value" />
```

| Property | Description | Type | Default | Version |
| --- | --- | --- | --- | --- |
| allowClear | whether allow clear | boolean | true |  |
| autofocus | get focus when component mounted | boolean | false |  |
| changeOnSelect | change value on each selection if set to true, see above demo for details | boolean | false |  |
| disabled | whether disabled select | boolean | false |  |
| displayRender | render function of displaying selected options, you can use #displayRender="{labels, selectedOptions}" | `({labels, selectedOptions}) => VNode` | `labels => labels.join(' / ')` |  |
| expandTrigger | expand current item when click or hover, one of 'click' 'hover' | string | 'click' |  |
| fieldNames | custom field name for label and value and children | object | `{ label: 'label', value: 'value', children: 'children' }` |  |
| getPopupContainer | Parent Node which the selector should be rendered to. Default to `body`. When position issues happen, try to modify it into scrollable content and position it relative. | Function(triggerNode) | () => document.body |  |
| loadData | To load option lazily, and it cannot work with `showSearch` | `(selectedOptions) => void` | - |  |
| notFoundContent | Specify content to show when no result matches. | string \| slot | 'Not Found' |  |
| options | data options of cascade | [Option](#option)[] | - |  |
| placeholder | input placeholder | string | 'Please select' |  |
| showSearch | Whether show search input in single mode. | boolean \| [object](#showsearch) | false |  |
| size | input size, one of `large` `default` `small` | string | `default` |  |
| suffixIcon | The custom suffix icon | string \| VNode \| slot | - |  |
| value(v-model) | selected value | string\[] \| number\[] | - |  |
| expandIcon | Customize the current item expand icon | slot | - | 3.0 |
| maxTagCount | Max tag count to show. `responsive` will cost render performance | number \| `responsive` | - | 3.0 |
| maxTagPlaceholder | Placeholder for not showing tags | v-slot \| function(omittedValues) | - | 3.0 |
| dropdownClassName | additional className of popup overlay | string | - | 3.0 |
| dropdownStyle | additional style of popup overlay | CSSProperties | {} | 3.0 |
| open | set visible of cascader popup | boolean | - | 3.0 |
| placement | use preset popup align config from builtinPlacements：`bottomLeft` `bottomRight` `topLeft` `topRight` | string | `bottomLeft` | 3.0 |
| tagRender | Customize tag render when `multiple` | slot | - | 3.0 |
| multiple | Support multiple or not | boolean | - | 3.0 |
| searchValue | Set search value，Need work with `showSearch` | string | - | 3.0 |

### showSearch

Fields in `showSearch`:

| Property | Description | Type | Default |
| --- | --- | --- | --- |
| filter | The function will receive two arguments, inputValue and option, if the function returns true, the option will be included in the filtered set; Otherwise, it will be excluded. | `function(inputValue, path): boolean` |  |
| limit | Set the count of filtered items | number \| false | 50 |
| matchInputWidth | Whether the width of result list equals to input's | boolean |  |
| render | Used to render filtered options, you can use #showSearchRender="{inputValue, path}" | `function({inputValue, path}): VNode` |  |
| sort | Used to sort filtered options. | `function(a, b, inputValue)` |  |

### events

| Events Name | Description | Arguments | version |
| --- | --- | --- | --- | --- |
| change | callback when finishing cascader select | `(value, selectedOptions) => void` | - |  |
| dropdownVisibleChange | callback when popup shown or hidden | `(value) => void` | - | 3.0 |
| search | callback when input value change | `(value) => void` | - | 1.5.4 |

### Option

```ts
interface Option {
  value: string | number;
  label?: VNode;
  disabled?: boolean;
  children?: Option[];
}
```

## Methods

| Name    | Description  |
| ------- | ------------ |
| blur()  | remove focus |
| focus() | get focus    |
