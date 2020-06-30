# demogit

1 Mỗi branch (task) chỉ có duy nhất một commit 

Nếu đã push nhiều commit thì có thể giải quyết như sau :
Step 1: xem log có bao nhiêu commit : 
    ```
    git log --oneline
    ```
Step 2: Rebase số commit đó về một commit 
```
git rebase -i HEAD~n
```
Step 3 : edit commit cần gộp từ `pick` thành `fixup` sau đó save lại

Step 4 : Push lên 
```
    git push origin branchName -f 
```
Step 5: tạo PR vào develop 

2 Task nào cần cần release thì sẽ tạo branch từ `staging` với tên là release/abccc 

Step 1 : create branch 

```
    git checkout -b release/abc
```
Step 2 : Lấy những commit của các task cần release 
```
    git cherry-pick commitTaskId
```
Step 3: push 

```
    git push origin  release/abccc
```
Step 4 : tạo PR vào branch stg 