# counting_ice-drink
dfs 알고리즘을 이용해 음료수를 얼려서 아이스크림의 개수를 출력해라
세로: N개 가로:M개 얼음의틀 형태를 입력하고 구멍이난 부분을 0 그렇지 않으면 1 이다. 
한번에 만들 수 있는 아이스크림 개수를 출력해보아라!

 #python code

 N,M=map(int,input().split())
cage=[list(map(int,input())) for _ in range(N)]
count=0
def dfs(x,y):
    if x<=-1 or x>=N or y<=-1 or y>=M:
        return False
    if cage[x][y]==0:
        cage[x][y]=1
        dfs(x-1,y)
        dfs(x+1,y)
        dfs(x,y-1)
        dfs(x,y+1)
        return True
    return False
    
for i in range(N):
    for j in range(M):
        if dfs(i,j)==True:
            count+=1
print(count)
