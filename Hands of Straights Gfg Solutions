class Solution {
    static boolean isStraightHand(int N, int groupSize, int hand[]) {
        // code here
        if (groupSize == 1) {
            return true;
        }
        
        if (((N & 1) ^ (groupSize & 1)) == 1) {
            return false;
        }
        
        Map<Integer, Integer> tmap = new TreeMap<>();
        
        for (int h: hand) {
            tmap.put(h, tmap.getOrDefault(h, 0) + 1);
        }
        
        for (int key: tmap.keySet()) {
            while (tmap.get(key) > 0) {
                for (int i = 0 ; i < groupSize ; i++) {
                    if (!tmap.containsKey(key+i) || tmap.getOrDefault(key+i, 0) == 0) {
                        return false;
                    }
                }
                
                for (int i = 0 ; i < groupSize ; i++) {
                    tmap.put(key+i, tmap.get(key+i) - 1);
                }
            }
        }
        
        return true;
    }
}
