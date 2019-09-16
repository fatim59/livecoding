# livecoding#TABLE
   
 MODULE 
 
 title_md
 
 descripton
 
 statut
 
 date_ajout
 
 date_upd
  
 
 
 SEMAINE
 
 title
 
 description
 
 date_ajout
 
 date_upd
 
 statut
 
md_id
 
 
 
 
 TEST
 
 title
 
 description
 
 date_ajout
 
 date_upd
 
 statut
 
 semaine_id
 
 
 
 QUESTION
 
 title
 
 description
 
 statut
 
 text_id
 
 
 REPONSE
 
 point
 
 description
 
 statut
 
 id_question
 
 id_user
 
class module(models.Models): 
    title = models.CharField(max_length=255)    
    description = models.TextField()
    statut = models.BooleanField(default=True)
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
            
            
            
            
    
class Semaine(models.Models):
    title = models.CharField(max_length=255)
    description = models.TextField()
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    statut = models.BooleanField(default=True)
    module_id = models.ForeignKey(Module,on_delete=models.CASCADE, related_name="module_semaine")
    
    
    
class  test(models.Modeles):
    title = models.CharField(max_length=255)
    description = models.TextField()
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    statut = models.BooleanField(default=True)
    semaine_id =  models.ForeignKey(semaine,on_delete = models.CASCADE, related_name = " "semaine_text")
   
    
class question(models.Models):
     title = models.CharField(max_length=255)
     description = model.TextField()
     statut = models.BooleanField(default=True)
     text_id =models.ForeignKey(tet,on_delete = models.CASCADE, related_name = "text_question")
    
    
    
class reponse(models.Models):
     description = model.TextField()
     point_question = model.Decimal.Field(max_digits=None,decimal_places=None)
     statut = models.BooleanField(default=True)
     question_id =models.ForeignKey(question,on_delete = models.CASCADE, related_name = "question_reponse")
        
    
