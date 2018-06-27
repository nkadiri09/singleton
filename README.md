# singleton


## Simple Singleton:
    
    public class Singleton {

        private static ingleton instance;

        private Singleton(){}

        public static synchronized Singleton getInstance(){
            if(instance == null){
                instance = new Singleton();
            }
            return instance;
        }
    }
    
## ThreadSafeSingleton
    public class ThreadSafeSingleton {

        private static ThreadSafeSingleton instance;

        private ThreadSafeSingleton(){}

        public static synchronized ThreadSafeSingleton getInstance(){
            if(instance == null){
                instance = new ThreadSafeSingleton();
            }
            return instance;
        }
    }
    
## Double chcked locking.

      public static ThreadSafeSingleton getInstanceUsingDoubleLocking(){
          if(instance == null){
              synchronized (ThreadSafeSingleton.class) {
                  if(instance == null){
                      instance = new ThreadSafeSingleton();
                  }
              }
          }
          return instance;
      }
