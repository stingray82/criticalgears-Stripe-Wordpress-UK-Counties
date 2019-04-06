# criticalgears-Stripe-Wordpress-UK-Counties
UK Modifications for Critical Gears wordpress Stripe Processor (http://www.criticalgears.com/product/stripe-payment-terminal-wordpress/)  this could also work on all there payment processors, if they use the same format


# How to edit and select UK as default country and your county as the default county if you only do local work, or have no international customers you are able to delete the other states/counties.

1) Open Terminal/index.php line approximately 402 and copy and paste the contents of counties.php into here it goes directly below this code:

                     <label>State/Province:</label>
                       <select style="width:250px;" name="state" id="state" class="long-field" onchange="checkFieldBack(this);">
                         <option value="">Please Select</option>
                         ** Counties.php contents go here **
                         
We are placing them at the top so they are the first selections our users see
                       
2) Go to line 46 //Request Variables
Find $country =  on default install it states:
$country = (!empty($_REQUEST["country"]))?strip_tags(str_replace("'","`",$_REQUEST["country"])):'US';
Change to
$country = (!empty($_REQUEST["country"]))?strip_tags(str_replace("'","`",$_REQUEST["country"])):'UK';

Then below this find the $state variable
$state = (!empty($_REQUEST["state"]))?strip_tags(str_replace("'","`",$_REQUEST["state"])):'';
and Change to the UK county you would like in this example we are going to change it to Derbyshire
$state = (!empty($_REQUEST["state"]))?strip_tags(str_replace("'","`",$_REQUEST["state"])):'Derbyshire';


Now save and reload and the default country code will be UK and County will be defaulted to derbyshire, and the UK counties will be our default options.
