# mountain-range-problem
hint catalan number
using namespace std;

void helper2(int n , string s, int i, int j){
    
    if(i==n &&j==n){  
                   // cout<<s<<endl;
                   int x=0; for(int k=0;k<2*n;k++){if(s[k]=='a'){x++;}else{break;}}
                    // cout<<--x<<endl;
              x--;
             x=n-1;
                    
                    int grid[n][2*n]={0};
                        for(int c=0;c<n;c++){
                        for(int d=0;d<2*n;d++){
                            grid[c][d]=0;
                        }
                    }
        
                    // vector<vector<int>grid(n,vector<int>(2*n,0));
                    
                    for(int index=0;index<2*n;index++){
                        if(s[index]=='a'){grid[x][index]=1;
                                          if(s[index+1]=='a'){x--;}
                                         }
                        if(s[index]=='b'){grid[x][index]=-1; 
                                        if(index+1<2*n && s[index+1]=='b'){x++;}
                                         }
                    }
                    
                    for(int c=0;c<n;c++){
                        for(int d=0;d<2*n;d++){
                            if(grid[c][d]==0){cout<<" ";}
                            if(grid[c][d]==1){cout<<"/";}
                            if(grid[c][d]==-1){cout<<"\\";}

                    }
                                                cout<<endl;
                    }
                   }
        
    
     if(i< n){ helper2(n,s+"a",i+1,j); }
     if(i>j){ helper2(n,s+"b",i,j+1);}
    
}


int main() {
 int n ;
    cin>>n;
    
    helper2(n,"",0,0);
    

    return 0;
}
