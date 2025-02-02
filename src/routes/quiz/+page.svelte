<script>
    import { onMount } from 'svelte';

    let resultText = ''; 
    let description = ''; 

    onMount(() => {
        const form = document.getElementById('vampireForm');
        if (form) {
            form.addEventListener('submit', function(event) {
                event.preventDefault();

                let nosferatuScore = 0;
                let draculaScore = 0;
                let carmillaScore = 0;
                let alucardScore = 0;

                const answers = [
                    document.querySelector('input[name="q1"]:checked')?.value,
                    document.querySelector('input[name="q2"]:checked')?.value,
                    document.querySelector('input[name="q3"]:checked')?.value,
                    document.querySelector('input[name="q4"]:checked')?.value,
                    document.querySelector('input[name="q5"]:checked')?.value
                ];

                if (!answers.every(answer => answer)) {
                    alert('Por favor, responda todas as perguntas.');
                    return;
                }

                answers.forEach(answer => {
                    if (['isolated', 'animals', 'terrifying', 'brutal', 'darkpast'].includes(answer)) {
                        nosferatuScore++;
                    } else if (['castle', 'humans', 'charismatic', 'leader', 'power'].includes(answer)) {
                        draculaScore++;
                    } else if (['elegant', 'bloodbags', 'sophisticated', 'seductive', 'immortal'].includes(answer)) {
                        carmillaScore++;
                    } else if (['battle', 'chaotic', 'guns', 'merciless', 'madness'].includes(answer)) {
                        alucardScore++;
                    }
                });

                if (nosferatuScore > draculaScore && nosferatuScore > carmillaScore && nosferatuScore > alucardScore) {
                    resultText = 'O Nosferatu';
                    description = 'Você é Nosferatu, a sombra da noite, o horror que rasteja nas trevas.Sua aparência grotesca e sua presença assustadora fazem com que até mesmo os mais corajosos tremam de medo. Você é um vampiro primitivo, um ser das sombras que prefere viver isolado, longe da sociedade humana. Alimenta-se com brutalidade, deixando um rastro de terror por onde passa. Seu corpo deformado é um reflexo de sua maldição eterna, condenado a vagar pela escuridão sem jamais conhecer o calor da vida. O sol é seu maior inimigo, e sua única companhia são os ratos e os ecos de seus próprios lamentos. Você não seduz nem encanta, apenas assombra. Fraqueza: Exposição à luz do sol, queima sua pele como fogo ardente.Poder: Aparência monstruosa que infunde medo profundo em suas vítimas.';
                } else if (draculaScore > nosferatuScore && draculaScore > carmillaScore && draculaScore > alucardScore) {
                    resultText = 'O Dracula';
                    description = 'Você é Drácula, o senhor da noite, o governante imortal que se alimenta do medo e da admiração. Com sua presença imponente e seu olhar penetrante, você comanda todos ao seu redor com uma mistura irresistível de carisma e ameaça. Seu castelo é um monumento ao poder e ao mistério, onde suas vítimas são atraídas como mariposas para a chama. Você tem um intelecto afiado, refinamento e uma sofisticação que fazem de você um predador nobre e cruel. Sua força é sobre-humana, e seu domínio sobre as trevas é absoluto. Quando deseja, pode se transformar em névoa ou morcego, desaparecendo como um fantasma. Você não precisa correr atrás de sua presa—ela vem até você, fascinada pelo seu magnetismo sombrio. Fraqueza: Uma estaca no coração pode pôr fim à sua imortalidade. Poder: Hipnotiza e domina suas vítimas apenas com o olhar.';
                } else if (carmillaScore > nosferatuScore && carmillaScore > draculaScore && carmillaScore > alucardScore) {
                    resultText = 'A Carmilla';
                    description = 'Você é Carmilla, a vampira sedutora, a predadora que dança entre a luxúria e a morte. Dona de uma beleza etérea e de uma presença envolvente, você não ataca, você conquista. Suas presas se entregam a você voluntariamente, hipnotizadas por sua doçura e pela promessa de uma eternidade ao seu lado. Seu mundo é luxuoso e envolto em mistério, cheio de véus de seda e segredos sussurrados ao luar. Você se move como uma sombra delicada, mas por trás do seu sorriso encantador esconde-se uma predadora impiedosa. Seus ataques são silenciosos e precisos, drenando a vida de suas vítimas enquanto elas ainda estão presas no êxtase do momento. Sua maior arma é o desejo que inspira nos outros um desejo que sempre termina em sangue. Fraqueza: Seu amor pela beleza e pelo prazer pode torná-la vulnerável. Poder: Sedução irresistível, capaz de encantar até os corações mais frios.';
                } else if (alucardScore > nosferatuScore && alucardScore > draculaScore && alucardScore > carmillaScore) {
                    resultText = 'O Alucard';
                    description = 'Você é Alucard, o caçador de vampiros que não conhece piedade. Ao contrário dos outros vampiros, você não é apenas um predador—você é um exterminador. Sua existência não é movida apenas pelo desejo de sangue, mas pela fúria e pela diversão em destruir tudo ao seu redor. Você é um guerreiro imortal, um monstro entre monstros, rindo na face do perigo enquanto mergulha em batalhas sangrentas. Sua personalidade caótica e sádica o torna imprevisível, e seus poderes são tão vastos que poucos ousam enfrentá-lo. Você pode invocar demônios, regenerar seu corpo e até se transformar em um enxame de criaturas da noite. O horror está no fato de que você não apenas aceita sua natureza destrutiva—você a abraça e a torna sua maior arma. Fraqueza: Sua sede por carnificina pode levá-lo a perder o controle. Poder: Força sobre-humana e habilidades de combate devastadoras.';
                } else {
                    resultText = 'Voce tem caracteristicas de varios vampiros';
                    description = 'Você é um vampiro híbrido, um enigma envolto em mistério. Diferente dos outros vampiros, você não se encaixa em uma única categoria. Em seu sangue correm ecos de diferentes linhagens, misturando características de poder, sedução, caos e horror. Você é um ser imprevisível, capaz de transitar entre a escuridão e a luxúria, entre o medo e a fúria. Seu destino é incerto—você será o próximo grande senhor das trevas ou cairá na destruição de sua própria natureza? Seja como for, uma coisa é certa: você é único, e o mundo nunca viu algo como você antes.';
                }
            });
        }
    });
</script>

<div class="container Dracula">
    <center><h1 style="font-family:Dracula">Qual Vampiro Voce e?</h1></center>
    <form id="vampireForm">

        <h3><p>Qual tipo de ambiente você prefere?</p></h3>
        <div class="radio-group">
            <input type="radio" id="q1_1" name="q1" value="isolated">
            <label for="q1_1">Ambiente isolado e sombrio</label>

            <input type="radio" id="q1_2" name="q1" value="castle">
            <label for="q1_2">Um castelo majestoso</label>

            <input type="radio" id="q1_3" name="q1" value="elegant">
            <label for="q1_3">Um lugar elegante e refinado</label>

            <input type="radio" id="q1_4" name="q1" value="battle">
            <label for="q1_4">O campo de batalha</label>
        </div>

        <h3><p>Como você prefere se alimentar?</p></h3>
        <div class="radio-group">
            <input type="radio" id="q2_1" name="q2" value="animals">
            <label for="q2_1">Animais</label>

            <input type="radio" id="q2_2" name="q2" value="humans">
            <label for="q2_2">Humanos</label>

            <input type="radio" id="q2_3" name="q2" value="bloodbags">
            <label for="q2_3">Sacos de sangue</label>

            <input type="radio" id="q2_4" name="q2" value="chaotic">
            <label for="q2_4">Absorvendo as almas de suas vítimas</label>
        </div>

        <h3><p>Como você se descreveria?</p></h3>
        <div class="radio-group">
            <input type="radio" id="q3_1" name="q3" value="terrifying">
            <label for="q3_1">Aterrorizante</label>

            <input type="radio" id="q3_2" name="q3" value="charismatic">
            <label for="q3_2">Carismático</label>

            <input type="radio" id="q3_3" name="q3" value="sophisticated">
            <label for="q3_3">Sofisticado</label>

            <input type="radio" id="q3_4" name="q3" value="guns">
            <label for="q3_4">Sádico</label>
        </div>

        <h3><p>Qual seu traço mais marcante?</p></h3>
        <div class="radio-group">
            <input type="radio" id="q4_1" name="q4" value="brutal">
            <label for="q4_1">Brutal e cruel</label>

            <input type="radio" id="q4_2" name="q4" value="leader">
            <label for="q4_2">Um líder nato</label>

            <input type="radio" id="q4_3" name="q4" value="seductive">
            <label for="q4_3">Sedutor e manipulador</label>

            <input type="radio" id="q4_4" name="q4" value="merciless">
            <label for="q4_4">Impiedoso e imortal</label>
        </div>

        <h3><p>Qual é sua principal motivação?</p></h3>
        <div class="radio-group">
            <input type="radio" id="q5_1" name="q5" value="darkpast">
            <label for="q5_1">Um passado sombrio</label>

            <input type="radio" id="q5_2" name="q5" value="power">
            <label for="q5_2">O desejo de poder</label>

            <input type="radio" id="q5_3" name="q5" value="immortal">
            <label for="q5_3">A busca pela imortalidade</label>

            <input type="radio" id="q5_4" name="q5" value="madness">
            <label for="q5_4">A sede por destruição</label>
        </div>

        <center><button type="submit"> Descobrir!</button></center>
    </form>
</div>

<div id="result">
    <center><h1 style="font-family:Dracula">{resultText}</h1></center>
    <h4><p>{description}</p></h4>
</div>

<style>
    @import url('https://fonts.googleapis.com/css2?family=UnifrakturMaguntia&display=swap');


    body {
        background-color: gray;
        color: #222;
        font-family: 'UnifrakturMaguntia', cursive;
        text-align: center;
    }

    button {
        background-color: red;
        color: white;
        font-size: 18px;
        border: none;
        padding: 10px 20px;
        cursor: pointer;
        border-radius: 5px;
        margin-top: 10px;
    }

    button:hover {
        background-color: darkred;
        box-shadow: 0px 0px 10px red;
    }

    h1 {
        color: red;
        font-size: 150px;
        text-shadow: 4px 4px black;

    }

    h3 {
        color: black        ;
        font-size: 30px;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;

        padding: 10px;
        border-radius: 5px;
    }
    
    h4 {
        color: black;
        font-size: 25px;
        font-family:'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    }

    .radio-group {
        display: flex;
        flex-direction: column;
        gap: 10px;
        align-items: center;
        margin-bottom: 20px;
    }

    input[type="radio"] {
        display: none;
    }

    label {
        background-color: black;
        color: white;
        padding: 10px;
        border-radius: 5px;
        font-size: 20px;
        cursor: pointer;
        transition: all 0.3s ease;
        display: block;
        width: 300px;
        text-align: center;
    }

    input[type="radio"]:checked + label {
        background-color: red;
        font-size: 24px;
        font-weight: bold;
        transform: scale(1.1);
    }
</style>
