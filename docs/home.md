# Mes notes sur le C#

```csharp
Public class Vehicule // penser à mettre public pour l'accessibilité sur le/les projet(s)
{
    #région Propriétés (snipet: prop tab_tab)
    // Propriétés relative aux caractèristiques de la classe.
    // Publiques car elles pouront être pertinentes hors de la classes => Heritage (Dérivation), Classe Abstraite et/ou polymorphisme.
    
    public string Marque { get; private set; }
    public string Modèle { get; private set; }
    public int Cylindrée { get; private set; }

    // Propriétés relative à l'expérience du chef.
    // Privées car elles ne concenent que le fonctionnement interne de la classe, et ne doivent pas être accessible de l'extérieur.
    private int ExperienceNeeded { get; set; }

    // Méthode publique : règles métier.
    public Chef(string firstname, string lastname)
    {
        FirstName = firstname;
        LastName = lastname;
        Level = 1;
    }
    
    public void Practice(Meal meal)
    {
        int exp = meal switch 
        {
            Rosbif => 60,
            Pizza => 30,
            _ => 10
        };

        Train(exp);
    }

    // Méthode privée : fonctionnement interne uniquement
    private void Train(int experience)
    {
        Experience += experience;
    }
} 
  ```
