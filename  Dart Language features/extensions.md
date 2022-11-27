# Extension functions

#### Explanatory example
 
    class Bidder {
        String name ='willam';
    }

    extension surname on Bidder {
        String withSurname (){
        return name + " Paulton";
     }
    }

From calling widget.

    Bidder bidder = Bidder();
        print(bidder.withSurname());





