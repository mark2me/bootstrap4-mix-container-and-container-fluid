# Bootstrap 4 for mix container and container-fluid
在 contaier 下也能實現單一側邊欄位延伸滿版


### Add New Code
Find below code on `scss/mixins/_grid-framework.scss`
```
.col#{$infix}-#{$i} {
    @include make-col($i, $columns);
}
```
        
After that add:
```
@if ( $i < $columns ){
    .col#{$infix}-#{$i}.col-full-l {
        flex: inherit;
        max-width: inherit;
        margin-left: calc( ( 100vw - 100% ) / -2 );
        width: calc( #{percentage( $i / $columns )} + ( 100vw - 100% ) / 2 );
    }
    .col#{$infix}-#{$i}.col-full-r {
        flex: inherit;
        max-width: inherit;
        margin-right: calc( ( 100vw - 100% ) / -2 );
        width: calc( #{percentage( $i / $columns )} + ( 100vw - 100% ) / 2 );
    }
}
```

Or directly replace it with my file `_grid-framework.scss`
```
scss/mixins/_grid-framework.scss
```


### rebuild
Rebuild you need css file like `scss/bootstrap.scss`, `scss/bootstrap-reboot.scss` or `scss/bootstrap-frid.scss` 


### Usage
Just add class `.col-full-l` or `.col-full-r` after class `col-*` like `class="col-lg-5 coll-full-l"`
