# DLAPP_Lab3
## 11/2 update
1. 原本的程式是每張圖片算出各class的AP再相加，但應該要全部圖片的同一個class算完AP再相加會是合理的。
2. 原本只要出現一個類別只有一個bounding box的話在計算AP上會有不合理的地方。
目前將以上兩點更正

## 10/31 update
### output rule
demo當天會是給好幾張圖片以及其ground truth(txt檔)，會需要請你們將每張圖片經過你們訓練好的yolov3 model預測出結果，並將結果用以下規定存成txt檔 : 
- gt的txt格式 : class x y w h
- predict的txt格式 : class confidence x y w h
注意請將x,y,w,h正規化到0~1

- 每一張圖片產生一個txt檔(其名稱請跟圖片一樣)
- txt檔中的每一row是一個bounding box
- bounding box中的每一個值請用空格分開

### notice
demo當天的圖片會以數字命名，所以在```metric.py```中會有根據檔名排序的動作去避免判斷到錯誤的預測結果
所以要測試的時候要注意檔案的命名
