# livecoding#TABLE
   
 MODULE 
 titre_md
 descripton
 statut
 
 SEMAINE
 titre
 date_ajout
 date_upd
 statut
md_id
 
 TEXT
 titre
 date_ajout
 date_upd
 statut
 semaine_id
 
 QUESTION
 quest_text
 point_quest
 statut
 text_id
 
classe module(models.Models): 
    title = models.CharField(max_length=255)
    description = models.TextField()
    statut = models.BooleanField(default=True)
    
class Semaine(models.Models):
    title = models.CharField(max_length=255)
    date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    statut = models.BooleanField(default=True)
    module_id = models.ForeignKey(Module,on_delete=models.CASCADE, related_name="module_semaine")
    
class  text(models.Modeles):
     title = models.CharField(max_length=255)
     date_add = models.DateTimeField(auto_now_add=True)
    date_upd = models.DateTimeField(auto_now=True)
    statut = models.BooleanField(default=True)
    semaine_id =  models.ForeignKey(semaine,on_delete = models.CASCADE, related_name = " "semaine_text")
   
    
class question(models.Models):
     question_text = model.TextField()
     point_question = model.Decimal.Field(max_digits=None,decimal_places=None)
     statut = models.BooleanField(default=True)
     text_id =models.ForeignKey(tet,on_delete = models.CASCADE, related_name = "text_question")
    
    
