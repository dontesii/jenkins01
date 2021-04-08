node {     
      def 
      этап приложения      ('Клонировать репозиторий') 
      {                
             
            checkout scm     
      }     
      stage ('Создать образ') {       
       
            app = docker.build ("dontesi/admon")     
       }     
      stage ('Test image') {           
            app.inside {             
             
             sh 'echo "Тесты пройдены"'         
            }     
        }     
       stage ('Push image') { 
                                                  docker.withRegistry ('https://registry.hub.docker.com', 'git') {            
       app.push ("$ {env.BUILD_NUMBER}")             
       app.push ("последний")         
              }     
           } 
        }
