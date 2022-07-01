# day1
/// bfs of the graph

#include <bits/stdc++.h>
using namespace std;

 // } Driver Code Ends
class Solution {
  public:
    // Function to return Breadth First Traversal of given graph.
    vector<int> bfsOfGraph(int V, vector<int> adj[]) {
        // Code here
        queue<int>Q;
        Q.push(0);
        vector<bool>vis(V,false);
        vis[0]=true;
        vector<int>vec;
        while(Q.empty()==false)
        {
            int u=Q.front();
            Q.pop();
            vec.push_back(u);
            for(int v:adj[u])
            {
                if(vis[v]==false)
                {
                    Q.push(v);
                    vis[v]=true;
                }
            }
        }
        return vec;
    }
};

// { Driver Code Starts.
int main() {
    int tc;
    cin >> tc;
    while (tc--) {
        int V, E;
        cin >> V >>

            E;

        vector<int> adj[V];

        for (int i = 0; i < E; i++) {
            int u, v;//jjjjjj
            cin >> u >> v;
            adj[u].push_back(v);
            // 		adj[v].push_back(u);
        }
        // string s1;
        // cin>>s1;
        Solution obj;
        vector<int> ans = obj.bfsOfGraph(V, adj);
        for (int i = 0; i < ans.size(); i++) {
            cout << ans[i] << " ";
        }
        cout << endl;
    }
    return 0;
}  // } Driver Code Ends
                    
                    
  //dfs of the graph
                     void dfs(int V,vector<int>adj[],vector<int>&vec,vector<bool>&vis,int s)
    {
        vis[s]=true;
        vec.push_back(s);
        for(int v:adj[s])
        {
            if(vis[v]==false)
            {
                dfs(V,adj,vec,vis,v);
            }
        }
    }
    vector<int> dfsOfGraph(int V, vector<int> adj[]) {
        // Code here
        vector<int>vec;
        vector<bool>vis(V,false);
        dfs(V,adj,vec,vis,0);
        return vec;
    }
 
 
 
 
 
                    
                    
                    
                    
                    
                    
                    
                    
                    
                    
                    
                    
