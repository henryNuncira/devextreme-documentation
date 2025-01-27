To configure node selection, use the following properties:

* [selectByClick](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#selectByClick)           
Enables selection by a click.

* [showCheckBoxesMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#showCheckBoxesMode)           
Adds checkboxes if you set this property to *"normal"* or *"selectAll"*. The latter mode additionally displays the "Select All" checkbox at the top of the TreeView.

* [selectionMode](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#selectionMode)             
Sets the selection mode to *"single"* or *"multiple"* (default).

* [onItemSelectionChanged](/Documentation/ApiReference/UI_Components/dxTreeView/Configuration/#onItemSelectionChanged)           
Specifies a function that is executed when a single node is selected or deselected.

In this tutorial, we enable selection by a click and use the single-node selection mode. Also, we specify the **onItemSelectionChanged** function to display the selected product, its picture, and price.

---
##### jQuery

    <!-- tab: index.js -->
    $(function(){
        $("#treeView").dxTreeView({ 
            // ...
            selectionMode: "single",
            selectByClick: true,        
            onItemSelectionChanged: function(e) {
                const selectedProduct = e.itemData;
                if(selectedProduct.price) {
                    $("#product-details").removeClass("hidden");
                    $("#product-details > img").attr("src", selectedProduct.image);
                    $("#product-details > .price").text("$" + selectedProduct.price);
                    $("#product-details > .name").text(selectedProduct.name);
                } else {
                    $("#product-details").addClass("hidden");
                }
            }
        });
    });

    <!-- tab: index.html -->
    <!DOCTYPE html>
    <html>
        <head>
            <!-- ... -->
        </head>
        <body class="dx-viewport">
            <div id="treeView"></div>
            <div id="product-details" class="hidden">
                <img src="" />
                <div class="name"></div>
                <div class="price"></div>
            </div>
        </body>
    </html>

    <!-- tab: index.css -->
    #treeView, #product-details {
        display: inline-block;
        width: 300px;
    }

    #product-details {
        vertical-align: top;
        width: 400px;
        height: 420px;
        margin-left: 20px;
    }

    #product-details > img {
        border: none;
        height: 300px;
        width: 400px;
    }

    #product-details > .name {
        text-align: center;
        font-size: 20px;
    }

    #product-details > .price {
        text-align: center;
        font-size: 24px;
    }

    .hidden {
        visibility: hidden;
    }


##### Angular

    <!-- tab: app.component.html -->
    <dx-tree-view ...
        selectionMode="single"
        [selectByClick]="true"
        (onItemSelectionChanged)="selectProduct($event)">
        <div *dxTemplate="let product of 'productTemplate'">
            {{ product.price ? product.name + "(" + product.price + ")" : product.name }}
        </div>
    </dx-tree-view>
    <div id="product-details" *ngIf="currentProduct.price">
        <img [src]="currentProduct.image" />
        <div class="name">{{currentProduct.name}}</div>
        <div class="price">${{ currentProduct.price }}</div>
    </div>

    <!-- tab: app.component.ts -->
    // ...
    export class AppComponent {
        // ...
        currentProduct: Product;

        constructor(service: ProductsService) {
            // ...
            this.currentProduct = this.products[0];
        } 

        selectProduct(e) {
            this.currentProduct = e.itemData;
        }
    }


    <!-- tab: app.component.css -->
    #treeView, #product-details {
        display: inline-block;
        width: 300px;
    }

    #product-details {
        vertical-align: top;
        width: 400px;
        height: 420px;
        margin-left: 20px;
    }

    #product-details > img {
        border: none;
        height: 300px;
        width: 400px;
    }

    #product-details > .name {
        text-align: center;
        font-size: 20px;
    }

    #product-details > .price {
        text-align: center;
        font-size: 24px;
    }

##### Vue

    <!-- tab: App.vue -->
    <template>
        <div>
            <DxTreeView ...
                selection-mode="single"
                :select-by-click="true"
                @item-selection-changed="selectProduct">
                <!-- ... -->
            </DxTreeView>
            <div id="product-details" v-if="currentProduct.price">
                <img :src="currentProduct.image" >
                <div class="name">{{ currentProduct.name }}</div>
                <div class="price">${{ currentProduct.price }}</div> 
            </div>
        </div>
    </template>

    <script>
    import DxTreeView from 'devextreme-vue/tree-view';
    import products from './products';

    export default {
        components: {
            DxTreeView
        },
        data() {
            return {
                // ...
                currentProduct: products[0],
            }
        },
        methods: {
            selectProduct(e) {
                this.currentProduct = e.itemData;
            }
        }
    }
    </script>

    <style>
        #treeView, #product-details {
            display: inline-block;
            width: 300px;
        }

        #product-details {
            vertical-align: top;
            width: 400px;
            height: 420px;
            margin-left: 20px;
        }

        #product-details > img {
            border: none;
            height: 300px;
            width: 400px;
        }

        #product-details > .name {
            text-align: center;
            font-size: 20px;
        }

        #product-details > .price {
            text-align: center;
            font-size: 24px;
        }
    </style>


##### React

    <!-- tab: App.js -->
    // ...
    function App() {
        const [selectedNode, setSelectedNode] = useState(products[0]);
        const selectProduct = (e) => {
            setSelectedNode(e.itemData);
        }
        // ...
        return (
            <div>
                <TreeView ...
                    selectionMode="single"
                    selectByClick={true}
                    onItemSelectionChanged={selectProduct}
                />
                {
                    selectedNode.price &&
                    <div id="product-details">
                        <img src={selectedNode.image}/>
                        <div className="name">{selectedNode.name}</div>
                        <div className="price">{`$${ selectedNode.price}`}</div>
                    </div>
                }
            </div>
        );
    }

    export default App;

    <!-- tab: App.css -->
    #treeView, #product-details {
        display: inline-block;
        width: 300px;
        margin: 10px;
    }

    #product-details {
        vertical-align: top;
        width: 400px;
        height: 420px;
        margin-left: 20px;
    }

    #product-details > img {
        border: none;
        height: 300px;
        width: 400px;
    }

    #product-details > .name {
        text-align: center;
        font-size: 20px;
    }

    #product-details > .price {
        text-align: center;
        font-size: 24px;
    }

---
