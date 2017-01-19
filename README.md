# AMAZON DASH BUTTON TIME TO MEAL IFTTT HACK

A script that makes a notification in a Telegram "Home" group to say that is meal time using an Amazon dash button

Code based on the great work of [Aaron bell](http://www.aaronbell.com/)

More info and setup at:

<a href="http://www.aaronbell.com/how-to-hack-amazons-wifi-button/">http://www.aaronbell.com/how-to-hack-amazons-wifi-button/</a>

Made by Julián Caro Linares

* email: jcarolinares@gmail.com
* twitter: @jcarolinares


# Materials

* Amazon dash button (It doesn't matter the product brand)
* A computer with Python (better a Raspberry Pi connected to your Wifi network)
* Telegram account
* IFTTT account

# SETUP

## Amazon Dash button setup

I followed the steps that Ted Benson says in <a href="https://medium.com/@edwardbenson/how-i-hacked-amazon-s-5-wifi-button-to-track-baby-data-794214b0bdd8#.2ovluz4wx">his hack:</a>

"The first thing you need to do is configure your buttons to send messages when you push them but not actually order anything. When you get a Dash button, Amazon gives you a list of setup instructions to get going. Just follow this list of instructions, but don’t complete the final step — don’t select the particular product you want ordered.

The last step for the Huggies button, for example, is to select which of several Huggies products you want. Just don’t answer this question and you won’t have to worry about actually buying anything."

In the last step, when you have to choose your product, just close the app.

### Knowing your dash button MAC adress

You can use the Python scripts that Ted Benson uses in [his hack](https://medium.com/@edwardbenson/how-i-hacked-amazon-s-5-wifi-button-to-track-baby-data-794214b0bdd8#.2ovluz4wx).

If this programs doesn't work for you, install in your smartphone an App like [Fing](https://play.google.com/store/apps/details?id=com.overlook.android.fing).

## IFTTT Recipe Setup

1. Go to [IFTTT](https://ifttt.com/discover) and create a new Applet

2. Select the **Maker** channel and the option **Receive a web request**.

3. In **Event name** put the name **dash_meal_time**

4. Now you can choose the service that you want, in my case I choosed the **Telegram Channel**

5. Before you go fordward, you need to create a group in telegram with the people that you want to share the notifications. Remember to also invite the **@IFTTT** bot and use the **/connect_group** option.

6. Now that you have your group, select in IFTTT the action **Send message**

7. Select your group in the **Target chat** option, in the message text, put a message like:

"Time: {{OccurredAt}}<br><br><a><strong>¡¡¡MEAL TIME!!!</strong></a>"  

The web page preview it's not important.

To finish remember to save your recipe.


## Python script setup

Now that you know your dash button MAC adress and your IFTT recipe done. It's time to setup your Python script.

Open **meal_time_ifft_script.py** and change:

* ifttt_key = '9cn3847ntc8394tn8-ab' **You'll find your IFTT key in your Maker channel Setup**

* '74234223434a' : 'dash_glad' **Put your amazon dash button MAC at the left, be careful with uppercases and lowercases**.

## Use it

Now execute your python script using

sudo python meal_time_ifft_script.py

Now put your button near your kitchen andyou push it. Everything should work. Enjoy it!

=============

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Licencia Creative Commons" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">AMAZON DASH BUTTON TIME TO MEAL IFTTT HACK</span> por <span xmlns:cc="http://creativecommons.org/ns#" property="cc:attributionName">Julián Caro Linares</span> licensed by <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.<br /><br />
