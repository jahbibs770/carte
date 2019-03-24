# carte
Projet 2 CARTE BANCAIRE

Réalisé par : Samba Bailo BA

Notre projet porte sur la réalisation d’une carte bancaire

Objectif :

	Générer une carte de crédit
	Générer des numéros de cartes valide
	Fonctionnement de l’algorithme de Luhn
Le projet a été réalisé en javascript
Tout d’abord nous avons une classe appelé Verification.js contenant la methode verifier_code()

export default class Verification {
    verifier_code(){
        throw new Error();
    }
}

Une classe Visa.js qui étend la classe Verification ou la methode verifier_code est redéfinie :
Pour que la carte VISA soit correctement identifiée, il faut que le préfixe commence par 4. Ce numéro de préfixe sert d’identifiant unique pour un type de carte particulier. De ce fait on a utilisé l’algorithme de Luhn pour le contrôle de saisi .
  verifier_code(){
            
            var cardno = new RegExp(/^(?:4[0-9]{12}(?:[0-9]{3})?)$/);
            if(cardno.test(this._number))

Une classe Mastercard.js qui étend aussi la classe Verificattion ou la redefinition de la méthode verifier_code()
  verifier_code(){
  
            var cardno = new RegExp(/^(?:5[1-5][0-9]{14})$/);
         if(cardno.test(this._number))

Remarque : Ces classes héritières vont importer toujours  la classe mère

Une classe American_Express qui fait la même chose 
verifier_code(){
            var cardno = new RegExp(/^(?:3[47][0-9]{13})$/);
            if(cardno.test(this._number))

Une classe teste main.js qui permet de :
•	De créer une prompt sur le fichier test.html
•	Permettre la saisie dans le prompt
•	Recuperer l’élément saisi dans le prompt 
•	Le comparer avec la méthode verifier_code pour les 3 cartes 
•	Retourne la carte appropriée après vérification 
•	Sinon retourne un numéro de carte invalide

•	let a = prompt("Entrer un numero de carte");
•	    let v = new Visa(a);
•	    let m = new Mastercard(a);
•	    let n = new American_Express(a);
•	
•	    let x = v.verifier_code();
•	    let y = m.verifier_code();
•	    let z = n.verifier_code();
•	    if(x===true)
•	    console.log("carte visa")
•	    if(y===true)
•	    console.log("Mastercard")
•	    if(z===true)
•	    console.log("American_Express")     
•	    if(!x  && !y && !z) 
•	    console.log("numero de carte incorrecte")

test.html
 

 

 

 

