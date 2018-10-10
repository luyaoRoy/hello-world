/*# hello-world
just my first repository
hi,I am cly*/
//合并子函数 
procedureTForm1.MergePass(vardatas:arrayofInteger;left,mid, right:Integer); 
var
tmpArr:arrayofInteger; 
arrLen:Integer; 
i,k:Integer; 
begin1,begin2,end1,end2:Integer;
begin arrLen:=right-left+1;
SetLength(tmpArr,arrLen); 
begin1:=left; 
end1:=mid; 
begin2:=mid+1; 
end2:=right; 
k:=0; 
while((begin1<=end1)and(begin2<=end2))do 
begin 
if(datas[begin1]<datas[begin2])then 
begin 
tmpArr[k]:=datas[begin1]; 
Inc(begin1); 
end else begin tmpArr[k]:=datas[begin2]; 
Inc(begin2); 
end; 
inc(k);
end;
while(begin1<=end1)do 
begin
tmpArr[k]:=datas[begin1]; 
Inc(begin1); 
Inc(k); 
end; 
while(begin2<=end2)do 
begin 
tmpArr[k]:=datas[begin2]; 
Inc(begin2); 
Inc(k); 
end; 
fori:=0to(right-left)do 
begin 
datas[left+i]:=tmpArr[i]; 
end; 
end; //排序主函数，left是数组左下标，0开始。right是数组右下标。 
procedureTForm1.MergeSort(vardatas:arrayofInteger;left,right:Integer); 
var mid:Integer; 
i:Integer; 
begin mid:=0; 
if(left<right)then 
begin 
mid:=(right+left)div2;
showLog('中间索引：'+inttostr(mid)); 
MergeSort(datas,left,mid); 
MergeSort(datas,mid+1,right); 
MergePass(datas,left,mid,right); 
showLog('--->'+getArrayString(datas));//显示数组中间状态
end; 
end; 
//调用方法：
procedureTForm1.btn1Click(Sender:TObject); 
var inArr:array[0..9]ofInteger; 
begin 
CopyMemory(@inArr[0],@CTabls[0],SizeOf(Integer)*10); 
showLog('输入数据：'+getArrayString(inArr));
MergeSort(inArr,0,High(inArr)); 
showLog('输出数据：'+getArrayString(inArr));
end;


