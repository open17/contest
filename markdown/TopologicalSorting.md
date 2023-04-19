# 拓扑排序
## 过程
1. 入度为0加入队列
2. 循环，后继节点入度-1，若为0加入队列
## 板子
```c++
//邻接表
vector<vector<int>> graph;
//入度
vector<int> indeg;
queue<int> q;
for(int i=0;i<numCourses;i++){
    if(indeg[i]==0)q.push(i);
}
vector<int>ans;
while(!q.empty()){
    int i=q.front();
    q.pop();
    ans.push_back(i);
    for(int j:graph[i]){
        indeg[j]--;
        if(indeg[j]==0){
            q.push(j);
        }
    }
}
```