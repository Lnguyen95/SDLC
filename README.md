# SDLC Text analyzer

    import java.io.BufferedReader;
    import java.io.FileReader;
    import java.io.IOException;
    import java.util.ArrayList;
    import java.util.Collections;
    import java.util.Comparator;
    import java.util.HashMap;
    import java.util.HashSet;
    import java.util.List;
    import java.util.Map.Entry;
    import java.util.Set;
    import java.io.*;

    public class Textanaly {

        public static void main(String[] args) {
        
        // created hashmap for counting words
        
        HashMap<String, Integer> wordCountMap = new HashMap<String, Integer>();
        BufferedReader reader = null;
        
        // created text file reader
        
        try {
        reader = new BufferedReader(new FileReader("C:\\Users\\Desktop\\Shakespear.txt."));
        String currentLine = reader.readLine();
        
        // created while loop to read each line
        
        while (currentLine != null) {
        String[] words = currentLine.toLowerCase().split(" ");
        sorter.add(new pair<String, Integer> (p0,p1));
        for (String word : words)
        {
        
        // created if else statement for each words counts 
        
        if(wordCountMap.containsKey(word)) {
        wordCountMap.put(word, wordCountMap.get(word)+1);
        } else {
        wordCountMap.put(word, 1);  
          }
        }
        currentLine = reader.readLine(); }
        
        // created new list from text file and sorted it
        
        Set<Entry<String, Integer>> entrySet = wordCountMap.entrySet();
        List<Entry<String, Integer>> list = new ArrayList<Entry<String,Integer>>(entrySet);
        Collections.sort(list, new Comparator<Entry<String, Integer>>() {
          public int compare(Entry<String, Integer> e1, Entry<String, Integer> e2) {
          return (e2.getValue().compareTo(e1.getValue()));
          }
        });
      
      // Display printout from text file and count repated worlds from desending order
      
      System.out.println("Repeated Words In Input File Are:");
      
      for (Entry<String, Integer> entry : list) {
        if (entry.getValue() > 1) {
          System.out.println(entry.getKey() + ":"+ entry.getValue());
          }
        }
      }
      catch (IOException e) {
        e.printStackTrace();
        }
          finally {
            try {
              reader.close(); 
              }
                catch (IOException e)
                {
                  e.printStackTrace();
                  }
                }
              }
            }
