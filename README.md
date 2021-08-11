## 簡易的聊天機器人資料庫 Heroku / MongoDB / LINE BOT

### MongoDB的資料庫架構步驟<br>
1.讀取資料庫(Database)<br>
2.讀取集合(Collection)<br>
3.文檔(Document)的CRUD(建立、閱讀、修改、刪除)<br>

↑上面三者的關係為：<br>
MongoClient的資料庫(Database)裡面，可以擁有多個集合(Collection)，相當於關聯式資料庫裡面的資料表(Table)，<br>
每個集合當中，存在取多筆資料，每一筆資料被稱作為一個文檔(Document)，這是屬於在MongoDB資料庫當中最末端的價值單元<br>
因此如果我們希望可以進行資料存取操作，首先要先建立一個資料庫與集合，才能把資料寫入其中<br>

### mongodb_function.py<br>
client: 一個透過pymongo建立的MongoDB連線<br>
db: 讀取clinet當中，名為MongoClient的Database<br>
col: 讀取db當中，名為Database的Collection<br>
dicMemberCheck(): 判斷key是否在指定的dictionary當中，若有則return True<br>
write_one_data(): 寫入資料data是dictionary<br>
write_many_datas(): 寫入多筆資料，data是一個由dictionary組成的list<br>
read_many_datas(): 讀取所有LINE的webhook event紀錄資料<br>
read_chat_records(): 讀取LINE的對話紀錄資料<br>
delete_all_data(): 刪除所有資料<br>
col_find(): 找到最新的一筆資料<br>

操作步驟：<br>
1.註冊MongoDB帳號，並且建立一個帳號建立資料庫<br>
2.將LINE@帳號的Channel Acess Token、Channel Secret置換成自己的<br>

[MongoDB官網](https://www.mongodb.com/)<br>
[LINE Developer官網](https://developers.line.biz/)<br>