<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>La Parole Vivante - Livre Évangélique</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .page {
            transform-style: preserve-3d;
            transition: transform 1s;
            transform-origin: left center;
        }
        .page.flipped {
            transform: rotateY(-180deg);
        }
        .page-content {
            backface-visibility: hidden;
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
        }
        .back-content {
            transform: rotateY(180deg);
        }
        .highlight-verse {
            animation: highlight 2s ease-in-out;
        }
        @keyframes highlight {
            0% { background-color: rgba(253, 230, 138, 0); }
            50% { background-color: rgba(253, 230, 138, 0.8); }
            100% { background-color: rgba(253, 230, 138, 0); }
        }
        .book-cover {
            background: linear-gradient(135deg, #1e3a8a 0%, #1e40af 100%);
            box-shadow: 0 10px 30px -5px rgba(0, 0, 0, 0.3);
        }
    </style>
</head>
<body class="bg-gray-100 font-sans">
    <div class="container mx-auto px-4 py-8">
        <h1 class="text-4xl font-bold text-center text-blue-900 mb-8">La Parole Vivante</h1>
        
        <div class="flex flex-col items-center">
            <!-- Livre interactif -->
            <div class="relative w-full max-w-2xl h-96 md:h-[500px] perspective-1000 mb-8">
                <!-- Couverture avant -->
                <div class="absolute w-full h-full book-cover rounded-lg shadow-xl flex flex-col items-center justify-center p-8 text-white cursor-pointer" id="front-cover" onclick="flipPage('front-cover', 'page1')">
                    <i class="fas fa-bible text-6xl mb-4"></i>
                    <h2 class="text-3xl font-bold mb-2">La Parole Vivante</h2>
                    <p class="text-xl text-center">Un voyage à travers les Écritures pour découvrir l'amour de Dieu</p>
                    <div class="mt-4 text-sm">Cliquez pour ouvrir</div>
                </div>
                
                <!-- Page 1 -->
                <div class="absolute w-full h-full page bg-white rounded-r-lg shadow-lg hidden" id="page1">
                    <div class="page-content p-8 overflow-y-auto">
                        <h3 class="text-2xl font-bold text-blue-900 mb-4">Introduction</h3>
                        <p class="mb-4">Bienvenue dans ce livre interactif conçu pour vous faire découvrir la merveilleuse Parole de Dieu. À travers ces pages, vous explorerez les vérités fondamentales de la Bible.</p>
                        <p class="mb-4">Dieu vous aime d'un amour éternel et veut avoir une relation personnelle avec vous. Ce livre vous guidera à travers ce message d'amour et de salut.</p>
                        <div class="bg-yellow-100 border-l-4 border-yellow-500 p-4 mb-4">
                            <p class="font-semibold">"Car Dieu a tant aimé le monde qu'il a donné son Fils unique, afin que quiconque croit en lui ne périsse point, mais qu'il ait la vie éternelle."</p>
                            <p class="text-right text-gray-600">- Jean 3:16</p>
                        </div>
                        <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded float-right" onclick="flipPage('page1', 'page2')">Suivant <i class="fas fa-arrow-right ml-2"></i></button>
                    </div>
                    <div class="page-content back-content p-8 overflow-y-auto bg-gray-50">
                        <!-- Contenu de l'arrière de la page 1 -->
                    </div>
                </div>
                
                <!-- Page 2 -->
                <div class="absolute w-full h-full page bg-white rounded-r-lg shadow-lg hidden" id="page2">
                    <div class="page-content p-8 overflow-y-auto">
                        <h3 class="text-2xl font-bold text-blue-900 mb-4">Le Message Central</h3>
                        <p class="mb-4">La Bible nous révèle que tous les êtres humains sont pécheurs et séparés de Dieu (Romains 3:23). Mais Dieu, dans son grand amour, a pourvu à une solution parfaite.</p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                            <div class="bg-blue-50 p-4 rounded-lg">
                                <h4 class="font-bold text-blue-800 mb-2">Le Problème</h4>
                                <ul class="list-disc pl-5 text-sm">
                                    <li class="mb-1">Le péché nous sépare de Dieu</li>
                                    <li class="mb-1">Nous méritons le jugement</li>
                                    <li class="mb-1">Nous ne pouvons nous sauver nous-mêmes</li>
                                </ul>
                            </div>
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-bold text-green-800 mb-2">La Solution</h4>
                                <ul class="list-disc pl-5 text-sm">
                                    <li class="mb-1">Jésus est mort pour nos péchés</li>
                                    <li class="mb-1">Il est ressuscité pour notre justification</li>
                                    <li class="mb-1">Le salut est un don gratuit</li>
                                </ul>
                            </div>
                        </div>
                        
                        <div class="bg-green-100 border-l-4 border-green-500 p-4 mb-4">
                            <p class="font-semibold">"Car le salaire du péché, c'est la mort; mais le don gratuit de Dieu, c'est la vie éternelle en Jésus-Christ notre Seigneur."</p>
                            <p class="text-right text-gray-600">- Romains 6:23</p>
                        </div>
                        
                        <div class="flex justify-between">
                            <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-4 py-2 rounded" onclick="flipPage('page2', 'page1')"><i class="fas fa-arrow-left mr-2"></i> Précédent</button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded" onclick="flipPage('page2', 'page3')">Suivant <i class="fas fa-arrow-right ml-2"></i></button>
                        </div>
                    </div>
                    <div class="page-content back-content p-8 overflow-y-auto bg-gray-50">
                        <!-- Contenu de l'arrière de la page 2 -->
                    </div>
                </div>
                
                <!-- Page 3 -->
                <div class="absolute w-full h-full page bg-white rounded-r-lg shadow-lg hidden" id="page3">
                    <div class="page-content p-8 overflow-y-auto">
                        <h3 class="text-2xl font-bold text-blue-900 mb-4">Le Chemin du Salut</h3>
                        <p class="mb-4">Recevoir le salut est simple, mais cela demande une décision personnelle. Voici les étapes bibliques pour devenir enfant de Dieu :</p>
                        
                        <div class="space-y-4 mb-6">
                            <div class="flex items-start">
                                <div class="bg-blue-600 text-white rounded-full w-8 h-8 flex items-center justify-center flex-shrink-0 mr-3 mt-1">1</div>
                                <div>
                                    <h4 class="font-bold text-blue-800">Reconnaître son état de pécheur</h4>
                                    <p class="text-sm">"Tous ont péché et sont privés de la gloire de Dieu" (Romains 3:23)</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start">
                                <div class="bg-blue-600 text-white rounded-full w-8 h-8 flex items-center justify-center flex-shrink-0 mr-3 mt-1">2</div>
                                <div>
                                    <h4 class="font-bold text-blue-800">Croire en Jésus-Christ</h4>
                                    <p class="text-sm">"Crois au Seigneur Jésus et tu seras sauvé" (Actes 16:31)</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start">
                                <div class="bg-blue-600 text-white rounded-full w-8 h-8 flex items-center justify-center flex-shrink-0 mr-3 mt-1">3</div>
                                <div>
                                    <h4 class="font-bold text-blue-800">Recevoir Christ par la foi</h4>
                                    <p class="text-sm">"À tous ceux qui l'ont reçue, elle a donné le pouvoir de devenir enfants de Dieu" (Jean 1:12)</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start">
                                <div class="bg-blue-600 text-white rounded-full w-8 h-8 flex items-center justify-center flex-shrink-0 mr-3 mt-1">4</div>
                                <div>
                                    <h4 class="font-bold text-blue-800">Confesser Christ comme Seigneur</h4>
                                    <p class="text-sm">"Si tu confesses de ta bouche le Seigneur Jésus, et si tu crois dans ton cœur que Dieu l'a ressuscité des morts, tu seras sauvé." (Romains 10:9)</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="bg-purple-100 border-l-4 border-purple-500 p-4 mb-4">
                            <p class="font-semibold">"Voici, je me tiens à la porte, et je frappe. Si quelqu'un entend ma voix et ouvre la porte, j'entrerai chez lui, je souperai avec lui, et lui avec moi."</p>
                            <p class="text-right text-gray-600">- Apocalypse 3:20</p>
                        </div>
                        
                        <div class="flex justify-between">
                            <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-4 py-2 rounded" onclick="flipPage('page3', 'page2')"><i class="fas fa-arrow-left mr-2"></i> Précédent</button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded" onclick="flipPage('page3', 'page4')">Suivant <i class="fas fa-arrow-right ml-2"></i></button>
                        </div>
                    </div>
                    <div class="page-content back-content p-8 overflow-y-auto bg-gray-50">
                        <!-- Contenu de l'arrière de la page 3 -->
                    </div>
                </div>
                
                <!-- Page 4 -->
                <div class="absolute w-full h-full page bg-white rounded-r-lg shadow-lg hidden" id="page4">
                    <div class="page-content p-8 overflow-y-auto">
                        <h3 class="text-2xl font-bold text-blue-900 mb-4">Prière de Salut</h3>
                        <p class="mb-4">Si vous désirez recevoir Jésus-Christ comme votre Sauveur personnel, vous pouvez le faire maintenant par la prière. Voici un modèle de prière :</p>
                        
                        <div class="bg-pink-50 border border-pink-200 rounded-lg p-6 mb-6">
                            <p class="italic text-center mb-4">"Seigneur Jésus, je reconnais que je suis pécheur et que j'ai besoin de ton salut. Je crois que tu es mort sur la croix pour mes péchés et que tu es ressuscité pour ma justification.</p>
                            <p class="italic text-center mb-4">Je t'ouvre la porte de mon cœur et je te reçois comme mon Sauveur et Seigneur personnel. Merci de me pardonner tous mes péchés et de faire de moi un enfant de Dieu.</p>
                            <p class="italic text-center">Je te confesse maintenant comme mon Seigneur et je veux te suivre tous les jours de ma vie. Amen."</p>
                        </div>
                        
                        <p class="mb-4 text-green-700 font-semibold">Si vous avez prié cette prière avec sincérité, la Bible déclare que vous êtes maintenant un enfant de Dieu ! (Jean 1:12)</p>
                        
                        <div class="bg-blue-100 border-l-4 border-blue-500 p-4 mb-4">
                            <p class="font-semibold">"Si quelqu'un est en Christ, il est une nouvelle créature. Les choses anciennes sont passées; voici, toutes choses sont devenues nouvelles."</p>
                            <p class="text-right text-gray-600">- 2 Corinthiens 5:17</p>
                        </div>
                        
                        <div class="flex justify-between">
                            <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-4 py-2 rounded" onclick="flipPage('page4', 'page3')"><i class="fas fa-arrow-left mr-2"></i> Précédent</button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded" onclick="flipPage('page4', 'page5')">Suivant <i class="fas fa-arrow-right ml-2"></i></button>
                        </div>
                    </div>
                    <div class="page-content back-content p-8 overflow-y-auto bg-gray-50">
                        <!-- Contenu de l'arrière de la page 4 -->
                    </div>
                </div>
                
                <!-- Page 5 -->
                <div class="absolute w-full h-full page bg-white rounded-r-lg shadow-lg hidden" id="page5">
                    <div class="page-content p-8 overflow-y-auto">
                        <h3 class="text-2xl font-bold text-blue-900 mb-4">Vie Nouvelle en Christ</h3>
                        <p class="mb-4">Félicitations ! Si vous avez reçu Christ, vous commencez maintenant une nouvelle vie. Voici quelques conseils pour grandir spirituellement :</p>
                        
                        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-6">
                            <div class="bg-indigo-50 p-4 rounded-lg">
                                <div class="text-indigo-600 text-2xl mb-2"><i class="fas fa-book-bible"></i></div>
                                <h4 class="font-bold text-indigo-800 mb-2">Lire la Bible</h4>
                                <p class="text-sm">Commencez par l'Évangile de Jean pour mieux connaître Jésus.</p>
                            </div>
                            
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <div class="text-purple-600 text-2xl mb-2"><i class="fas fa-hands-praying"></i></div>
                                <h4 class="font-bold text-purple-800 mb-2">Prier quotidiennement</h4>
                                <p class="text-sm">Parlez à Dieu comme à un Père aimant.</p>
                            </div>
                            
                            <div class="bg-green-50 p-4 rounded-lg">
                                <div class="text-green-600 text-2xl mb-2"><i class="fas fa-people-group"></i></div>
                                <h4 class="font-bold text-green-800 mb-2">Rejoindre une église</h4>
                                <p class="text-sm">Trouvez une communauté chrétienne pour vous encourager.</p>
                            </div>
                        </div>
                        
                        <div class="bg-orange-100 border-l-4 border-orange-500 p-4 mb-4">
                            <p class="font-semibold">"Croissez dans la grâce et dans la connaissance de notre Seigneur et Sauveur Jésus-Christ."</p>
                            <p class="text-right text-gray-600">- 2 Pierre 3:18</p>
                        </div>
                        
                        <div class="text-center mt-8">
                            <h4 class="text-xl font-bold text-blue-900 mb-2">Versets à méditer</h4>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                                <div class="bg-white border border-gray-200 rounded p-3 cursor-pointer hover:bg-yellow-50" onclick="highlightVerse(this)">
                                    <p>"Je vous écris, petits enfants, parce que vos péchés vous sont pardonnés à cause de son nom."</p>
                                    <p class="text-right text-sm text-gray-600">1 Jean 2:12</p>
                                </div>
                                <div class="bg-white border border-gray-200 rounded p-3 cursor-pointer hover:bg-yellow-50" onclick="highlightVerse(this)">
                                    <p>"Il n'y a donc maintenant aucune condamnation pour ceux qui sont en Jésus-Christ."</p>
                                    <p class="text-right text-sm text-gray-600">Romains 8:1</p>
                                </div>
                                <div class="bg-white border border-gray-200 rounded p-3 cursor-pointer hover:bg-yellow-50" onclick="highlightVerse(this)">
                                    <p>"Si nous confessons nos péchés, il est fidèle et juste pour nous les pardonner, et pour nous purifier de toute iniquité."</p>
                                    <p class="text-right text-sm text-gray-600">1 Jean 1:9</p>
                                </div>
                                <div class="bg-white border border-gray-200 rounded p-3 cursor-pointer hover:bg-yellow-50" onclick="highlightVerse(this)">
                                    <p>"Je puis tout par celui qui me fortifie."</p>
                                    <p class="text-right text-sm text-gray-600">Philippiens 4:13</p>
                                </div>
                            </div>
                        </div>
                        
                        <div class="flex justify-between mt-6">
                            <button class="bg-gray-300 hover:bg-gray-400 text-gray-800 px-4 py-2 rounded" onclick="flipPage('page5', 'page4')"><i class="fas fa-arrow-left mr-2"></i> Précédent</button>
                            <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded" onclick="closeBook()">Fermer le livre</button>
                        </div>
                    </div>
                    <div class="page-content back-content p-8 overflow-y-auto bg-gray-50">
                        <!-- Contenu de l'arrière de la page 5 -->
                    </div>
                </div>
                
                <!-- Couverture arrière -->
                <div class="absolute w-full h-full book-cover rounded-lg shadow-xl flex flex-col items-center justify-center p-8 text-white hidden" id="back-cover">
                    <i class="fas fa-cross text-6xl mb-4"></i>
                    <h2 class="text-3xl font-bold mb-2">Que Dieu vous bénisse !</h2>
                    <p class="text-xl text-center mb-4">Continuez à grandir dans la foi et à partager cette bonne nouvelle avec d'autres.</p>
                    <button class="bg-white text-blue-600 hover:bg-gray-100 px-6 py-2 rounded-full font-semibold" onclick="reopenBook()">Ouvrir à nouveau</button>
                    <div class="mt-6 text-sm">
                        <p>"Que la grâce du Seigneur Jésus-Christ, l'amour de Dieu, et la communion du Saint-Esprit soient avec vous tous."</p>
                        <p class="text-right">2 Corinthiens 13:14</p>
                    </div>
                </div>
            </div>
            
            <!-- Navigation pour mobile -->
            <div class="flex justify-center space-x-4 md:hidden">
                <button class="bg-blue-600 text-white p-3 rounded-full" onclick="navigateBook(-1)"><i class="fas fa-arrow-left"></i></button>
                <button class="bg-blue-600 text-white p-3 rounded-full" onclick="navigateBook(1)"><i class="fas fa-arrow-right"></i></button>
            </div>
        </div>
        
        <!-- Section témoignages -->
        <div class="max-w-4xl mx-auto mt-16">
            <h2 class="text-3xl font-bold text-center text-blue-900 mb-8">Témoignages de Transformation</h2>
            
            <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <div class="text-yellow-500 text-2xl mb-3"><i class="fas fa-quote-left"></i></div>
                    <p class="italic mb-4">"Ce livre m'a ouvert les yeux sur l'amour de Dieu. J'ai accepté Christ et ma vie a complètement changé."</p>
                    <div class="flex items-center">
                        <div class="bg-blue-600 text-white rounded-full w-10 h-10 flex items-center justify-center mr-3">M</div>
                        <div>
                            <p class="font-semibold">Marc, 32 ans</p>
                            <p class="text-sm text-gray-600">Paris</p>
                        </div>
                    </div>
                </div>
                
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <div class="text-yellow-500 text-2xl mb-3"><i class="fas fa-quote-left"></i></div>
                    <p class="italic mb-4">"Après des années de recherche, j'ai enfin trouvé la paix en Jésus grâce à ce message simple et clair."</p>
                    <div class="flex items-center">
                        <div class="bg-pink-600 text-white rounded-full w-10 h-10 flex items-center justify-center mr-3">S</div>
                        <div>
                            <p class="font-semibold">Sophie, 28 ans</p>
                            <p class="text-sm text-gray-600">Lyon</p>
                        </div>
                    </div>
                </div>
                
                <div class="bg-white p-6 rounded-lg shadow-md">
                    <div class="text-yellow-500 text-2xl mb-3"><i class="fas fa-quote-left"></i></div>
                    <p class="italic mb-4">"J'étais sceptique au début, mais la vérité de la Parole de Dieu a touché mon cœur. Maintenant je suis sauvé!"</p>
                    <div class="flex items-center">
                        <div class="bg-green-600 text-white rounded-full w-10 h-10 flex items-center justify-center mr-3">T</div>
                        <div>
                            <p class="font-semibold">Thomas, 45 ans</p>
                            <p class="text-sm text-gray-600">Marseille</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Section partage -->
        <div class="max-w-2xl mx-auto mt-16 text-center">
            <h2 class="text-3xl font-bold text-blue-900 mb-4">Partagez ce message d'espoir</h2>
            <p class="mb-6">Cette bonne nouvelle est trop précieuse pour la garder pour vous-même. Partagez ce livre avec vos amis et proches.</p>
            
            <div class="flex justify-center space-x-4">
                <button class="bg-blue-800 hover:bg-blue-900 text-white px-6 py-3 rounded-full flex items-center">
                    <i class="fab fa-facebook-f mr-2"></i> Partager
                </button>
                <button class="bg-green-600 hover:bg-green-700 text-white px-6 py-3 rounded-full flex items-center">
                    <i class="fab fa-whatsapp mr-2"></i> Envoyer
                </button>
                <button class="bg-red-500 hover:bg-red-600 text-white px-6 py-3 rounded-full flex items-center">
                    <i class="fas fa-envelope mr-2"></i> Email
                </button>
            </div>
        </div>
    </div>

    <script>
        let currentPage = 'front-cover';
        const pageOrder = ['front-cover', 'page1', 'page2', 'page3', 'page4', 'page5', 'back-cover'];
        
        function flipPage(fromId, toId) {
            const fromElement = document.getElementById(fromId);
            const toElement = document.getElementById(toId);
            
            if (fromId === 'front-cover') {
                fromElement.classList.add('hidden');
                toElement.classList.remove('hidden');
                currentPage = toId;
                return;
            }
            
            if (toId === 'back-cover') {
                fromElement.classList.add('hidden');
                toElement.classList.remove('hidden');
                currentPage = toId;
                return;
            }
            
            fromElement.classList.add('flipped');
            
            setTimeout(() => {
                fromElement.classList.add('hidden');
                fromElement.classList.remove('flipped');
                toElement.classList.remove('hidden');
                currentPage = toId;
            }, 1000);
        }
        
        function closeBook() {
            flipPage(currentPage, 'back-cover');
        }
        
        function reopenBook() {
            document.getElementById('back-cover').classList.add('hidden');
            document.getElementById('front-cover').classList.remove('hidden');
            currentPage = 'front-cover';
        }
        
        function navigateBook(direction) {
            const currentIndex = pageOrder.indexOf(currentPage);
            const newIndex = currentIndex + direction;
            
            if (newIndex >= 0 && newIndex < pageOrder.length) {
                const newPage = pageOrder[newIndex];
                flipPage(currentPage, newPage);
            }
        }
        
        function highlightVerse(element) {
            element.classList.add('highlight-verse');
            setTimeout(() => {
                element.classList.remove('highlight-verse');
            }, 2000);
        }
        
        // Animation d'ouverture automatique après 3 secondes
        setTimeout(() => {
            if (currentPage === 'front-cover') {
                document.getElementById('front-cover').classList.add('hover:scale-105');
                setTimeout(() => {
                    document.getElementById('front-cover').classList.remove('hover:scale-105');
                }, 500);
            }
        }, 3000);
    </script>
</body>
</html>
