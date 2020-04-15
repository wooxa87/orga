In these times it is advisable to stay at home to reduce the risk of infection and spreading the virus, but everybody needs to go shopping from time to time. However, you never know if your store is overcrowded or even worse, if there is a queue in front of the store. To solve this problem, we from the SafeMarket team, developed the idea to stay safe and simply check the actual store status and wait for your shopping time slot from home during the #wirvsvirus hackathon. 

SafeMarket is a digital reservation system for customers to book easily a shopping ticket, using the SafeMarket app or booking a ticket with the hotline. Ideally when the supermarket is not overcrowded to reduce the waiting queues in front of the stores. The result is that the stores would be used more evenly and the risk of the infection for customers and employees will be reduced also, while the shopping experience is increased, because of less people and less waiting times. Also, the solution considers walk-in customers by giving the shop owner the choice how many customers should be in the store and how many of them are allowed as walk-in customers or customers with a SafeMarket ticket.

For the first rough solution our team implemented three parts during the hackathon: 
1. a flutter app for the customer to book a ticked
2. a vue.js app for the shop owner and doorman to maintain the store and check the tickets
3. a backend as web app in C#, to bring everything together 

While the hackathon the target was to get a first solution running, but this point changed directly after the hackathon when we merged together with other teams, that had similar ideas and then after we successfully joined the “Solution Enabler” program supported by the German government. 

The focus we are working on right now is, to bring the SafeMarket solution live to the real markets. To reach that goal we had to evaluate our artifacts and compare them with the core requirements, to setup a scalable and easy to use solution. We started to move our backend to a serverless architecture that is auto scalable using a FaaS platform. Also, we continuously developed our customer app, that is already deployed in a first beta stadium in the [Google Play Store](https://play.google.com/store/apps/details?id=com.safe_market.reservation_system_customer&hl=de)

Stay tuned.
