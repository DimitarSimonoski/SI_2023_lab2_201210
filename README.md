Втора лабораториска вежба по Софтверско инженерство
Димитар Симоноски, индекс 201210
Control Flow Graph
Сликата е во repo-то.
Цикломатска комплексност

Според методот на броење како што можеме да видиме на сликата горе, цикличната комплексност е 14, и 23 според формулата број на 40 – 25 + 4*2.

Тест случаи според критериумот Every Branch 
1. [User==null, Password==null, Email==null ] - во овој случај и само во овој случај програмта ќе го помине низ 1-2 branchot, дека корсникот или не внел password или
Email или само пратил се празно, по влезот во „ user==null || user.getPassword()==null || user.getEmail()==null “ програмата фрла RuntimeException поминува низ 2-25 branch-от што ја прекинува програмата и му покажува на корисникот „Mandatory information missing!“.
2. [User!=null, Username==null, Pass:”12345678”, Mail:”dimitarsimonoskihotmailcom”] - 
3. [User!=null, Username==null, Pass:”12345678”, Mail:”dimitar.simonoski@hotmail.com”]
4.[User!=null, Username==Dimitar(new user), Pass:”12345678”, Mail:”dimitar.simonoski@hotmail.com(new mail)”]
5.[User!=null, Username==Dimitar(existing user), Pass:”12345678”, Mail:”dimitar.simonoski@hotmail.com(new mail)”]
6. [User!=null, Username==Dimitar(new user), Pass:”12345678”, Mail:”dimitar.simonoski@hotmail.com(existing mail)”]
7.[User!=null, Username==Dimitar(new user), Pass:”Dimitar”, Mail:”dimitar.simonoski@hotmail.com(new mail)”]
8. [User!=null, Username==Dimitar(new user), Pass:”123456 78”, Mail:”dimitar.simonoski@hotmail.com(new mail)”]
9.[User!=null, Username==Dimitar(new user), Pass:”1234567!”, Mail:”dimitar.simonoski@hotmail.com(new mail)”]
Тест случаи според критериумот Multiple Condition на 	if (user==null || user.getPassword()==null || user.getEmail()==null). 

1.[“user!=null”,“pass123”,“dimitar.simonoski@hotmail.com”]
2. [“user=null”,“pass123”,“dimitar.simonoski@hotmail.com”]
3.[“user!=null”,“null”,“dimitar.simonoski@hotmail.com”]
4. [“user!=null”,“pass123”,“null”]
