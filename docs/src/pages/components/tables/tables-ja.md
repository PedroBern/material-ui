---
title: Tableコンポーネント
components: Table, TableBody, TableCell, TableFooter, TableHead, TablePagination, TableRow, TableSortLabel
---

# Tables

<p class="description">データテーブルには、データのセットが表示されます。 それらは完全にカスタマイズできます。</p>

[Data tables](https://material.io/design/components/data-tables.html) は情報を見やすく表示する方法です。 Cardなどの他のプライマリーコンテンツを埋め込むことができます。

Data tables では次のものを含めることができます:

- 対応の可視化
- ナビゲーション
- データを照会および操作するためのツール

ツールを含めるときは、ツールをテーブルの真上、アタは真下に配置します。

## Structure

Data tableの上部には、列名をリストするヘッダー行があり、その後にデータ用の行が続きます。

ユーザーがデータを選択または操作する必要がある場合は、チェックボックスを各行に付ける必要があります。

アクセシビリティのために、最初の列は `<th>` 要素に設定され、 `スコープ` は `"row"`です。 これにより、スクリーンリーダーは行と列の名前でセルの値を識別できます。

## Simple Table

飾り気のないシンプルな例です。

{{"demo": "pages/components/tables/SimpleTable.js"}}

## Dense Table

簡単な例ではの緻密なテーブル詳細

{{"demo": "pages/components/tables/DenseTable.js"}}

## Sorting & Selecting

この例では、カスタム ` Toolbar `使用して、 ` Checkbox ` とクリック可能な行を選択に使用する方法を示します。 列見出しのスタイル設定に役立つように `TableSortLabel` コンポーネントを使用します。

テーブルは水平スクロールを示すために固定幅が与えられています。 ページ付けコントロールがスクロールするのを防ぐために、TablePaginationコンポーネントはTableの外側で使用されます。 （下記の ['カスタムテーブルページネーションアクション'の例](#custom-table-pagination-action) は、TableFooter内のページネーションを示しています。）

{{"demo": "pages/components/tables/EnhancedTable.js"}}

## Customized tables

コンポーネントのカスタマイズ例を次に示します。 詳細については、 [オーバーライドのドキュメントページ](/customization/components/)を参照してください。

{{"demo": "pages/components/tables/CustomizedTables.js"}}

### Custom pagination options

It's possible to customise the options shown in the "Rows per page" select using the `rowsPerPageOptions` prop. You should either provide an array of:

- **numbers**, each number will be used for the option's label and value.
    
    ```jsx
    <TablePagination rowsPerPageOptions={[10, 50]} />
    ```

- **objects**, the `value` and `label` keys will be used respectively for the value and label of the option (useful for language strings such as 'All').
    
    ```jsx
    <TablePagination rowsPerPageOptions={[10, 50, { value: -1, label: 'All' }]} />
    ```

### Custom pagination actions

The `Action` property of the `TablePagination` component allows the implementation of custom actions.

{{"demo": "pages/components/tables/CustomPaginationActionsTable.js"}}

## Fixed header

An example of a table with scrollable rows and fixed column headers. It leverages the `stickyHeader` prop (⚠️ no IE 11 support).

{{"demo": "pages/components/tables/StickyHeadTable.js"}}

## Spanning Table

A simple example with spanning rows & columns.

{{"demo": "pages/components/tables/SpanningTable.js"}}

## Virtualized Table

In the following example, we demonstrate how to use [react-virtualized](https://github.com/bvaughn/react-virtualized) with the `Table` component. これは200行をレンダリングし、より多くを簡単に処理できます。 仮想化はパフォーマンスの問題に役立ちます。

{{"demo": "pages/components/tables/ReactVirtualizedTable.js"}}

## 補完プロジェクト

より高度な使用例では、以下を利用できます。

### material-table

![Stars](https://img.shields.io/github/stars/mbrn/material-table.svg?style=social&label=Stars) ![npmダウンロード](https://img.shields.io/npm/dm/material-table.svg)

[material-table](https://github.com/mbrn/material-table) is a simple and powerful Datatable for React based on Material-UI Table with some additional features. They support many different use cases (editable, filtering, grouping, sorting, selection, i18n, tree data and more). 参照するといいでしょう。

{{"demo": "pages/components/tables/MaterialTableDemo.js"}}

### その他

- [dx-react-grid-material-ui](https://devexpress.github.io/devextreme-reactive/react/grid/): A data grid for Material-UI with paging, sorting, filtering, grouping and editing features ([paid license](https://js.devexpress.com/licensing/)).
- [mui-datatables](https://github.com/gregnb/mui-datatables): Responsive data tables for Material-UI with filtering, sorting, search and more.
- [tubular-react](https://github.com/unosquare/tubular-react): A Material-UI table with local or remote data-source. Featuring filtering, sorting, free-text search, export to CSV locally, and aggregations.

## アクセシビリティ

(WAI tutorial: https://www.w3.org/WAI/tutorials/tables/)

### Caption

A caption functions like a heading for a table. Most screen readers announce the content of captions. Captions help users to find a table and understand what it’s about and decide if they want to read it.

{{"demo": "pages/components/tables/AcccessibleTable.js"}}