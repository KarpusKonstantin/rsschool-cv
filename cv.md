# Desktop App Developer (Delphi)

## 1. First Name, Last Name

**Konstantin Karpus**

## 2. Contact Info
 
***e-mail :*** ks@wintecs.by;

## 3. Summary

I want to learn and discover something new in software development

## 4. Skills 
+ Delphi
+ FireBird DataBase
+ HTML5 
+ CSS3 

## 5. Code examples

```
  if P11 = '_INIT_COMPLECT_ORDER' then
  begin
    with MainForm, DM, DM_Registry do
    begin
      if (ActiveMDIChild <> nil) then
      begin
        if (ActiveMDIChild is TNewPostingForm)  then
        begin
          with (ActiveMDIChild as TNewPostingForm) do
          begin
            QR.Close;
            QR.SQLs.SelectSQL.Text:= Format('SELECT DISTINCT ORDERNO FROM %s', [OrderTB]);
            QR.Open;

            S := '';
            QR.First;
            while not QR.Eof do
            begin
              OrderNo := QR.FieldByName('Orderno').AsString;
              OrderNo := UpperCase(OrderNo);

              OrderNo := Format('''%s''',[OrderNo]);

              StringAddItem(S,OrderNo,',');
              QR.Next;
            end;

            frDSet_ComplectList.Close;
            frDSet_ComplectList.SelectSQL.Clear;
            frDSet_ComplectList.SelectSQL.Add('SELECT GRP, ORDERNO, POSNO, NAME, ARTICLE, COLOR, SIZE, UNITNAME, SUM(NUMBER) AS NUMBER, TOTALNUMBER FROM OTK_COMPLECTLIST');
            frDSet_ComplectList.SelectSQL.Add(Format('WHERE ORDERNO IN (%s)',[S]));
            frDSet_ComplectList.GroupByClause := 'GRP, ORDERNO, POSNO, NAME, ARTICLE, COLOR, SIZE, TOTALNUMBER, UNITNAME';
            frDSet_ComplectList.OrderClause := 'GRP, ORDERNO, POSNO, ARTICLE';
            frDSet_ComplectList.Open;
          end;
        end;
      end;
    end;

    ParValue := S;
  end;
````    

## 6. Experience

+  [WinTecs CRM](http://wintecs.by/product/wintecs-crm.html)
   
## 7. Education

+ **BSUIR**
  Facultet of telecommunication
   
## 8. English

I can understanding and reading with vocabulary

