///Bismillahir Rahmanir Rahim
///Author: Tanvir Ahmmad
///CSE,Islamic University,Bangladesh
#include<bits/stdc++.h>
using namespace std;
typedef long long ll;

const int N=1e5+5;
vector<int>graph[N];
int colour[N],parent[N];
int cycle_start=-1,cycle_end=-1;

void dfs(int u)
{
    colour[u]=1;
    for(int i=0; i<graph[u].size(); i++)
    {
        int v=graph[u][i];

        if(colour[v]==0)
        {
            parent[v]=u;
            dfs(v);
        }
        else if(colour[v]==1 && parent[u]!=v)
        {
            cycle_start=v;
            cycle_end=u;
            return ;
        }
    }
}

int main()
{
    int node,edge,u,v,flag=0;
    memset(colour,0,sizeof colour);
    memset(parent,-1,sizeof parent);

    cin>>node>>edge;
    while(edge--)
    {
        cin>>u>>v;
        graph[u].push_back(v);
        graph[v].push_back(u);
    }

    for(int i=1; i<=node; i++)
        if(colour[i]==0)
        {
            parent[i]=i;
            dfs(i);
            if(cycle_start!=(-1) && cycle_end!=(-1))
            {
                flag=1;
                vector<int>ans;
                int cnt=2,temp=cycle_start;
                ans.push_back(cycle_start);
                while(cycle_start!=cycle_end)
                {
                    cycle_start=parent[cycle_start];
                    ans.push_back(cycle_start);
                    cnt++;
                }
                ans.push_back(temp);
                cout<<cnt<<endl;
                for(int i=0;i<ans.size();i++) cout<<ans[i]<<" ";
                cout<<endl;
                break;
            }
        }

    if(!flag) cout<<"IMPOSSIBLE"<<endl;

    return 0;
}
///Alhamdulillah
