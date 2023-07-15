---
title: "Angular material - How to make header & column sticky"
description - A post on how to make header and first column sticky in Angular Material tables
date: 2021-07-06T12:22:30+05:30
categories:
  - blog
tags:
  - angular
  - tech
---

Setting up a sticky header and first column in Angular Material tables can be a bit tricky for some developers. However, with the help of directives and a few configuration steps, you can achieve this desired functionality with ease.

Follow the below steps

- Open your Angular project and navigate to the desired component.

- Identify the HTML structure of your table component by inspecting it or referring to your codebase.

```
 <table mat-table [dataSource]="dataSource" matSort>

  <!-- Sticky header -->
  <ng-container matColumnDef="header">
    <th mat-header-cell *matHeaderCellDef mat-sort-header sticky>Header</th>
  </ng-container>

  <tr mat-header-row *matHeaderRowDef="displayedColumns; sticky: true"></tr>

  <!-- First column -->
  <ng-container *ngFor="let column of columns" [matColumnDef]="column">
    <td mat-cell *matCellDef="let element" [sticky]="column === firstColumnName">{{ element[column] }}</td>
  </ng-container>

  <tr mat-row *matRowDef="let row; columns: displayedColumns;"></tr>

</table>

```
  In the code above, we apply the sticky directive to the mat-header-cell element of the header. This directive makes the header row sticky, ensuring it remains fixed at the top while scrolling. Additionally, we use the sticky: true attribute on the matHeaderRowDef directive to specify that the header row should remain sticky.

  For the first column, we apply the [sticky] attribute to the matCellDef directive with a condition column === firstColumnName. This attribute binds the sticky behavior to the first column only. Make sure to replace 'firstColumnName' with the actual name of your first column.
  
- Add CSS styles (optional)

```
 th.mat-header-cell[sticky], td.mat-cell.sticky-column {
  background-color: #f5f5f5; /* Light gray background */
}
```

All Done, you can run your angular application and observe the sticky header and first column in action. 

PS. The same functionality can be achieved by using creating custom directive and using CSS but this is a easier way to achieve the same. In case you need more customizability you can opt for the alternative.