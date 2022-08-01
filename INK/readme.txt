原始src code:
資料集為url形式
將此url轉換為xml形式
利用rdlib建成graph之後丟入sparql
用extractor得到neighbor
建立dataset(論文格式)
之後跟下面說的一樣!


src code

ex_ver2:　刪掉CreditScore、Balance、Salary ---> train_wo_num_data.tsv
ex_ver3:  全部資料集                       ---> train_full.tsv
ex_ver4:  全部資料集，但將CreditScore、Balance、Salary依照區間進行分類  ---> train_full_seg.tsv


運作方式:
先將資料集整理成論文中給的格式，將node之間的關係建立成sparse matrix
將sparse matrix與label丟入運算出acc & rules

計算方式:
將label做log_betabin的precompute (不知道為什麼要做這個)
用random forest的方式找到rules 
利用得到的rules去計算acc