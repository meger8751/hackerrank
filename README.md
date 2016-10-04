# hackerrank

    boolean checkBST(Node root) {
        
        if(root == null)  return true;

        return helper(root, -1,  10001);
     
        
    }


    private boolean helper(Node root, int min, int max) {
        
        if(root.left == null && root.right == null) return true;
        
        if(root.left == null) { 
            
            if(root.right.data > root.data && root.right.data < max) {
                
                return helper(root.right, root.data, max);
            
            }
            
            return false;
            
        }
        
        if(root.right == null) {
            
            if(root.left.data < root.data && root.left.data > min) {
                
                return helper(root.left, min, root.data);
                
            }
            
            return false;
            
        }
        

        if(root.left.data < root.data && root.right.data > root.data && root.left.data > min && root.right.data <                 max) {
            
            return helper(root.left, min, root.data) && helper(root.right, root.data, max);
            
        }
        
        return false;
   
    }
