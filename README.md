# Experiments with Mermaid diagrams and MathJax formulas

Github Enterprise 3.7 supports Mermaid diagrams, see [Creating Diagrams](https://docs.github.com/en/enterprise-server@3.7/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams).

Use the [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid) VS Code extension for creating these diagrams.

## Example

A simple class diagram:

```mermaid
classDiagram
    Time "1 Time" -- "*" Sale
    Customer "1 Customer" -- "* Sales" Sale
    Category "1 Category" -- "* Products" Product
    Product <|-- FoodProduct
    Product <|-- NonFoodProduct
    Product "1 Product" -- "* Sales" Sale 
    Sale "*" -- "1 SalesOrganization" SalesOrganization
    SalesOrganization "0..1 Superordinate" <-- SalesOrganization
    
    class Time {
      Date: Edm.Date ~~id~~
      Month: Edm.String
      Quarter: Edm.String
      Year: Edm.Int16
    }
    
    class Category {
      ID: Edm.String ~~id~~
      Name: Edm.String
    }
    
    class Product {
      ID: Edm.String ~~id~~
      Name: Edm.String
      Color: Edm.String
      TaxRate: Edm.Decimal
    }
    
    class FoodProduct {
      Rating: Edm.Byte
    }
    
    class NonFoodProduct {
      RatingClass: Edm.String
    }
    
    class Customer {
      ID: Edm.String ~~id~~
      Name: Edm.String
      Country: Edm.String
    }
    
    class Sale {
      ID: Edm.String ~~id~~
      Amount: Edm.Decimal
    }
    
    class SalesOrganization {
      ID: Edm.String ~~id~~
      Name: Edm.String
    }    
```

Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

This results in a runtime of 

$$t_\text{total} = t_A+\max(t_B,t_C) + t_D$$

with $t_x$ the runtime of step $x \in \\{ A,B,C,D \\}$.

## Instructions

Mermaid and MathJax are now natively supported when viewing `.md` files on GitHub. However, they are not automatically supported in [GitHub Pages](https://ralfhandl.github.io/mermaid-diagrams/). 

To enable MathJax in GitHub Pages, see [this stack overflow answer](https://stackoverflow.com/a/72931039).

To enable Mermaid in GitHub Pages, see [this stack overflow answer](https://stackoverflow.com/a/53893998).

Both solutions are applied in [_layouts/default.html](https://github.com/ralfhandl/mermaid-diagrams/blob/main/_layouts/default.html).
