# 학생과제 파일명 변경

```
for file in *.md; do                    
    newname=$(echo "$file" | sed -E 's/^.*(asmt-[0-9]{2}-[0-9]{3}-[0-9]{2}-[가-힣]+\.md)$/\1/');
    mv "$file" "$newname";
done
```