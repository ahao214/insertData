# insertData
向数据表中插入数万条数据


CREATE PROCEDURE insertAccountMst()
BEGIN

set @num = 1;
repeat
SET @floor = FLOOR(1 + (RAND() * 1000));
SET @floor1 = FLOOR(2 + (RAND() * 1000));
SET @floor2 = FLOOR(2 + (RAND() * 1000));


set @AccountID=concat(@floor,@floor1,@floor2);
set @AccountTypeID='01'; 
set @UserID='15091000000005';
set @UsableAmount='0';
set @FrozenAmount='0'; 
set @ValidDate='';
set @ActiveFlg='1';
set @NewUserId='15080100000001';
set @NewDateTime='2015-8-11';
set @UpdUserID='15080100000001';
set @UpdDateTime='2015-8-11';


INSERT
  INTO AccountMst(AccountID, AccountTypeID, UserID, UsableAmount, FrozenAmount, ValidDate, ActiveFlg, NewUserID, NewDateTime, UpdUserID, UpdDateTime)
  VALUES (@AccountID, @AccountTypeID, @UserID, @UsableAmount, @FrozenAmount, @ValidDate, @ActiveFlg,@NewUserId, @NewDateTime, @UpdUserID, @UpdDateTime);


    set @num =@num + 1;
until @num>200001 end repeat;    
END;

call insertAccountMst()



