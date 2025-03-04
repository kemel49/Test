<!--==============
বাইবেল তথ্যভান্ডার
==============
এই তথ্যভান্ডার ফাইলটি ডেভেলপারদেরকে সহজে বাইবেল সম্বন্ধীয় অ্যাপ্লিকেশন তৈরী করতে সাহায্য করার জন্য প্রকাশিত হয়েছে, ডেভেলপারদেরকে এই তথ্যভাণ্ডারের যেকোনো সংশোধনের অনুরোধ জানানোর জন্যও উৎসাহিত করা হচ্ছে।


ব্যবহার 
------

এই `শাখাটি` নিম্নোক্ত ভাষায় বাইবেলের sql ফাইল, sqlite তথ্যভান্ডার, XML এবং JSON তথ্যভান্ডার দ্বারা পরিপূর্ণ:
   #. `ইংরেজি <https://github.com/godlytalias/Bible-Database/tree/master/English>`_
   #. `মালায়ালম <https://github.com/godlytalias/Bible-Database/tree/master/Malayalam>`_
   #. `হিন্দী <https://github.com/godlytalias/Bible-Database/tree/master/Hindi>`_
   #. `তেলেগু <https://github.com/godlytalias/Bible-Database/tree/master/Telugu>`_
   #. `তামিল <https://github.com/godlytalias/Bible-Database/tree/master/Tamil>`_
   #. `কন্নড় <https://github.com/godlytalias/Bible-Database/tree/master/Kannada>`_
   #. `ওড়িয়া <https://github.com/godlytalias/Bible-Database/tree/master/Oriya>`_
   #. `গুজরাটি <https://github.com/godlytalias/Bible-Database/tree/master/Gujarati>`_
   #. `বাংলা <https://github.com/godlytalias/Bible-Database/tree/master/Bengali>`_
   #. `পাঞ্জাবি <https://github.com/godlytalias/Bible-Database/tree/master/Punjabi>`_
   #. `মারাঠি <https://github.com/godlytalias/Bible-Database/tree/master/Marathi>`_
   #. `জুলু <https://github.com/godlytalias/Bible-Database/tree/master/Zulu>`_
   #. `ইন্দোনেশিয়ান <https://github.com/godlytalias/Bible-Database/tree/master/Indonesian>`_
   #. `খোসা <https://github.com/godlytalias/Bible-Database/tree/master/Xhosa>`_
   #. `আফ্রিকান্স <https://github.com/godlytalias/Bible-Database/tree/master/Afrikaans>`_
   #. `সেপেডি <https://github.com/godlytalias/Bible-Database/tree/master/Sepedi>`_
   #. `নেপালি <https://github.com/godlytalias/Bible-Database/tree/master/Nepali>`_
   #. `হাঙ্গারিয়ান <https://github.com/godlytalias/Bible-Database/tree/master/Hungarian>`_

**SQL তথ্যভান্ডার**

SQL তথ্যভাণ্ডারে <> 
SQL Database is having fields ``Book``, ``Chapter``, ``Versecount``
which are of type INT and ``verse`` field which is VARCHAR.
The Book field starts from 0 and Chapter & Versecount from 1.
Below is a sample SQL query for fetching *John 3:16*

``Select Book,Chapter,Versecount,verse from bible where Book=42 and Chapter=3 and Versecount=16;``


**XML তথ্যভান্ডার**

XML Database is having fields ``Book``, ``Chapter``, ``Verse``
which are to having keys called 'id'.
The Book id starts from 0 and Chapter & Verse from 1.


**JSON তথ্যভান্ডার**

JSON Database have fields ``Verse`` & ``Verseid``. Verseid field is a unique id
which is a comibination of Book + Chapter + Verse. First two digits represents Book(0 - 65),
Second three digits represent Chapter and last three digits represent Verse.
For JSON Database, Book, Chapter and Verse starts from 0.
Below is a sample PHP code for fetching *John 3:16*;

>>> <?php
>>> $filecontent = file_get_contents("bible.json");
>>> $books = json_decode($filecontent);
>>> echo $books->Book[42]->Chapter[2]->Verse[15]->Verse;
>>> ?>

*Javascript Example*

>>> var bible;
>>> function readJsonFile() {
>>>     var rawFile = new XMLHttpRequest();
>>>     rawFile.overrideMimeType("application/json");
>>>     rawFile.onreadystatechange = function() {
>>>         if (rawFile.readyState === 4 && rawFile.status == "200") {
>>>             bible = JSON.parse(rawFile.responseText);
>>>         }
>>>     };
>>>     rawFile.open("GET", "bible.json", true);
>>>     rawFile.send();
>>> }
>>> 
>>> function queryverse(book, chapter, verse)
>>> {
>>>    return bible.Book[book - 1].Chapter[chapter - 1].Verse[verse - 1].Verse;
>>> }

ব্যবহারকারী এই রিপোটি ক্লোন করতে পারেন:

   git clone https://github.com/godlytalias/Bible-Database.git

সাহায্য, পর্যালোচনা ও পুনঃপরীক্ষা
--------------------
	#. ব্যবহারকারীরা তাদের মতামত, আলোচনা–সমালোচনা এই ইমেইল ঠিকানায় পাঠাতে পারেন godlytalias@yahoo.co.in 
	#. ডেভেলপাররা/সহযোগিতাকারীরা তাদের সমস্যা `উত্থাপন <https://github.com/godlytalias/Bible-Database/issues>` করতে পারেন অথবা `ইমেইল <mailto:godlytalias@yahoo.co.in>` করতে পারেন।
	#.পুল রিকোয়েস্টকে স্বাগত, যদি কোনো বাগ পাওয়া যায় তবে অনুগ্রহ করে ঠিক করে প্যাচগুলিকে পুশ করুন।

Credits
-------
`Wordproject® <http://wordproject.org>`_ থেকে তথ্য সংগ্রহ করে এই তথ্যভাণ্ডারটি তৈরী করা হয়েছে।

লাইসেন্স
-------

GNU GPL Version 3, 29 June 2007.

বিস্তারিত বিবরনের জন্য এই `লিঙ্কে <http://www.gnu.org/licenses/gpl-3.0.txt>`_
যান।

`Godly T.Alias <http://godlytalias.blogspot.com>`_ দ্বারা সর্বস্বত্ত সংরক্ষিত।

Copyright © 2015-->
