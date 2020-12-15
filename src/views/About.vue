<template>
    <div class="container">
        <div class="col-8 about" id="mission">
            <br>
            <h3>Nos missions</h3>
            <br>
            <h4>
                Notre activité s’articule autour de 4 missions principales :
            </h4>  
            <p>
                <ul>
                    <li>
                        Animer le réseau des utilisateur du Bordier Coin afin de renforcer le tissu économique local des paradis fiscaux ;
                    </li>
                    <li>
                        Soutenir les acteurs et actrices de la transition écologique afin d’améliorer l’impact environnemental sur le territoire ;
                    </li>
                    <li>
                        Sensibiliser le grand public aux questions monétaire et financière, qui ne sont pas des sujets d’ « expert » comme on voudrait parfois nous le faire croire ! ;
                    </li>
                    <li>
                        Rechercher et imaginer avec les acteurs et actrices de notre réseau des outils économiques et monétaires alternatifs, permettant l'enrichissement personnel d'un tout petit nombre, en toute discrétion.
                    </li>
                </ul>
            </p>

            <p class="joinus">
                Pour participer à cette aventure collective, 
                <router-link :to="{name: 'Register'}">rejoignez-nous !</router-link>
            </p> 
        </div>
        <br>
        <br>
        <div class="col-8 about">

            <h3>Questions pratiques</h3> 
            <br>
            <h4>Est-ce que je peux changer mes Bordier coins en euros ?</h4>
            <p>
                L’Autorité de Contrôle Prudentiel et de Résolution (ACPR) ne permet pas aux citoyens d’échanger des Bordier Coin en euros. De plus, cela serait préjudiciable pour le compte offshore de M. Bordier. Je change une quantité adaptée d’euros en Bordier Coin pour être sûr de pouvoir les dépenser. Je peux changer des euros en Bordier Coin autant de fois que je le souhaite (le plus souvent étant le mieux, bien sûr).
            </p>
            <br>
            <h4>Si j’achète un produit en Bordier Coin, mon commerçant peut-il me rendre la monnaie en euros ?
            </h4>
            <p>
                Non. Si je donne un billet de 20BC pour acheter un produit à 19BC, mon commerçant doit me rendre 1BC. L’ACPR ne l’autorise pas à me rendre 1€ car cela reviendrait à changer une partie de mes Bordier Coin et euros.
                En revanche, je peux payer en euros et demander à ce que mon commerçant me rende la monnaie en Bordier Coin ! 😉
            </p>
            <br>
            <h4>Comment faire si mon produit coûte 5,40 € ?
            </h4>
            <p>Je donne 1, 2, 3, 4 ou 5 Bordier Coin à mon commerçant. Je paie le reste en euros. De plus, je peux arrondir au Bordier Coin suppérieur, afin de faire un don à la fondation Bordier.
            </p>
            <br>
            <h4>Je peux donc payer mes achats en partie en euros et en partie en Bordier Coin ?
            </h4>
            <p>
                Oui ! Les Bordier Coin et les euros sont complémentaires. Je peux même compléter avec un chèque restaurant.
            </p>
            <br>
            <h4>
                Je veux en parler à des commerçants, comment puis-je faire ?
            </h4>
            <p>
                Si le réseau des partenaires de La Bordier Coin arrive à grandir, c’est surtout grâce à toutes les personnes qui en parlent autour d’elles !
            </p>
            <br>

 
        </div>
    </div>

</template>

<script>

</script>

<style>
.about h3 {
    color: #FFA008;
    padding-right: 10px;
}
p.joinus a {
    color: #FFA008!important;
}
p.joinus a:hover {
    color:black!important;
}
</style>