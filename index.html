<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Isolate It! Math Game</title>
    
    <!-- Tailwind CSS for Styling -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- React and ReactDOM -->
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    
    <!-- Babel for compiling JSX -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    
    <!-- Firebase SDKs -->
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-auth-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/10.7.1/firebase-firestore-compat.js"></script>
</head>
<body class="bg-slate-50">
    <div id="root"></div>

    <script type="text/babel">
        const { useState, useEffect } = React;
        
        // ==========================================
        // FIREBASE CONFIGURATION (OPTIONAL)
        // To make the leaderboard save across different computers, 
        // replace "YOUR_API_KEY" etc. with your actual Firebase config.
        // If left as is, the leaderboard will just work temporarily for the current session.
        // ==========================================
        const firebaseConfig = {
            apiKey: "YOUR_API_KEY",
            authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
            projectId: "YOUR_PROJECT_ID",
            storageBucket: "YOUR_PROJECT_ID.appspot.com",
            messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
            appId: "YOUR_APP_ID"
        };

        const isFirebaseConfigured = firebaseConfig.apiKey !== "YOUR_API_KEY";
        let app, auth, db;
        
        if (isFirebaseConfigured) {
            app = firebase.initializeApp(firebaseConfig);
            auth = firebase.auth();
            db = firebase.firestore();
        }

        // --- Inline Icon Components ---
        const IconRotateCcw = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><path d="M3 12a9 9 0 1 0 9-9 9.75 9.75 0 0 0-6.74 2.74L3 8"/><path d="M3 3v5h5"/></svg>);
        const IconXCircle = ({ className, title }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><circle cx="12" cy="12" r="10"/><path d="m15 9-6 6"/><path d="m9 9 6 6"/><title>{title}</title></svg>);
        const IconFlame = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><path d="M8.5 14.5A2.5 2.5 0 0 0 11 12c0-1.38-.5-2-1-3-1.072-2.143-.224-4.054 2-6 .5 2.5 2 4.9 4 6.5 2 1.6 3 3.5 3 5.5a7 7 0 1 1-14 0c0-1.153.433-2.294 1-3a2.5 2.5 0 0 0 2.5 2.5z"/></svg>);
        const IconTarget = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>);
        const IconTrophy = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><path d="M6 9H4.5a2.5 2.5 0 0 1 0-5H6"/><path d="M18 9h1.5a2.5 2.5 0 0 0 0-5H18"/><path d="M4 22h16"/><path d="M10 14.66V17c0 .55-.47.98-.97 1.21C7.85 18.75 7 20.24 7 22"/><path d="M14 14.66V17c0 .55.47.98.97 1.21C16.15 18.75 17 20.24 17 22"/><path d="M18 2H6v7a6 6 0 0 0 12 0V2Z"/></svg>);
        const IconPlay = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><polygon points="5 3 19 12 5 21 5 3"/></svg>);
        const IconHome = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><path d="m3 9 9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/><polyline points="9 22 9 12 15 12 15 22"/></svg>);
        const IconChevronRight = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><path d="m9 18 6-6-6-6"/></svg>);
        const IconCheckCircle2 = ({ className }) => (<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round" className={className}><circle cx="12" cy="12" r="10"/><path d="m9 12 2 2 4-4"/></svg>);

        // Basic profanity filter
        const badWords = ['badword1', 'badword2', 'swear', 'curse', 'dummy', 'stupid', 'idiot'];
        const filterName = (name) => {
          let isClean = true;
          const lowerName = name.toLowerCase();
          badWords.forEach(word => {
            if (lowerName.includes(word)) isClean = false;
          });
          return isClean ? name.trim() : 'Anonymous Student';
        };

        function App() {
          const [user, setUser] = useState(null);
          const [gameState, setGameState] = useState('menu'); 
          const [leaderboard, setLeaderboard] = useState([]);
          
          const [stats, setStats] = useState({ correct: 0, total: 0, currentStreak: 0, maxStreak: 0, score: 0 });
          const [equation, setEquation] = useState(null);
          const [step, setStep] = useState(1); 
          const [stepFeedback, setStepFeedback] = useState(null); 
          const [isPerfectQuestion, setIsPerfectQuestion] = useState(true);
          const [solveInput, setSolveInput] = useState('');
          const [playerName, setPlayerName] = useState('');
          const [strikes, setStrikes] = useState(0);

          const [passwordPrompt, setPasswordPrompt] = useState(false);
          const [passwordInput, setPasswordInput] = useState('');
          const [passwordError, setPasswordError] = useState(false);
          const [sortConfig, setSortConfig] = useState({ key: 'score', direction: 'desc' });

          // --- Setup & DB Init ---
          useEffect(() => {
            if (!isFirebaseConfigured) return;
            const initAuth = async () => {
              try { await auth.signInAnonymously(); } catch (err) { console.error("Auth failed:", err); }
            };
            initAuth();
            const unsubscribe = auth.onAuthStateChanged((u) => { setUser(u); });
            return () => unsubscribe();
          }, []);

          useEffect(() => {
            if (!isFirebaseConfigured || !user) return;
            try {
              const lbCollection = db.collection('artifacts').doc('isolate-it-game').collection('public').doc('data').collection('leaderboard');
              const unsubscribe = lbCollection.onSnapshot((snapshot) => {
                const data = snapshot.docs.map(doc => ({ id: doc.id, ...doc.data() }));
                data.sort((a, b) => b.score - a.score);
                setLeaderboard(data.slice(0, 50));
              });
              return unsubscribe;
            } catch (err) {
              console.error("Setup leaderboard error:", err);
            }
          }, [user]);

          // --- Game Logic ---
          const generateEquation = () => {
            const operations = ['add', 'subtract', 'multiply', 'divide'];
            const variables = ['x', 'y', 'a', 'b', 'm', 'n'];
            
            const op = operations[Math.floor(Math.random() * operations.length)];
            const variable = variables[Math.floor(Math.random() * variables.length)];
            
            let term, result, answer, eqString;

            if (op === 'add') {
              result = Math.floor(Math.random() * 15) + 5; 
              term = Math.floor(Math.random() * (result - 1)) + 1;
              answer = result - term;
              eqString = `${variable} + ${term} = ${result}`;
            } 
            else if (op === 'subtract') {
              answer = Math.floor(Math.random() * 18) + 2; 
              term = Math.floor(Math.random() * (answer - 1)) + 1;
              result = answer - term;
              eqString = `${variable} - ${term} = ${result}`;
            } 
            else if (op === 'multiply') {
              term = Math.floor(Math.random() * 8) + 2; 
              answer = Math.floor(Math.random() * Math.floor(20 / term)) + 1; 
              result = term * answer;
              eqString = `${term}${variable} = ${result}`;
            } 
            else if (op === 'divide') {
              term = Math.floor(Math.random() * 8) + 2; 
              result = Math.floor(Math.random() * Math.floor(20 / term)) + 1; 
              answer = term * result;
              eqString = `${variable} / ${term} = ${result}`;
            }

            setEquation({ op, variable, term, result, answer, string: eqString });
            setStep(1);
            setStepFeedback(null);
            setIsPerfectQuestion(true);
            setSolveInput('');
            
            setStats(prev => ({ ...prev, total: prev.total + 1 }));
          };

          const startGame = () => {
            setStats({ correct: 0, total: 0, currentStreak: 0, maxStreak: 0, score: 0 });
            setStrikes(0);
            setGameState('playing');
            generateEquation();
          };

          const handleMistake = (customMessage) => {
            const nextStrikes = strikes + 1;
            setStrikes(nextStrikes);
            setIsPerfectQuestion(false);
            setStats(prev => ({ ...prev, currentStreak: 0 }));
            
            if (nextStrikes >= 3) {
              setStepFeedback({ type: 'error', text: `Strike 3! Game Over.` });
              setTimeout(() => setGameState('gameover'), 2000);
            } else {
              setStepFeedback({ type: 'error', text: `${customMessage} (Strike ${nextStrikes}/3)` });
            }
          };

          const handleOpChoice = (choice) => {
            if (strikes >= 3) return;
            if (choice === equation.op) {
              setStepFeedback({ type: 'success', text: 'Correct! Now identify the inverse.' });
              setTimeout(() => { setStep(2); setStepFeedback(null); }, 1500);
            } else {
              handleMistake('Not quite. Look at what is happening to the variable.');
            }
          };

          const getInverseOp = (op) => {
            switch (op) {
              case 'add': return 'subtract';
              case 'subtract': return 'add';
              case 'multiply': return 'divide';
              case 'divide': return 'multiply';
              default: return '';
            }
          };

          const handleInverseChoice = (choice) => {
            if (strikes >= 3) return;
            if (choice === getInverseOp(equation.op)) {
              setStepFeedback({ type: 'success', text: 'Awesome! That is the correct inverse operation.' });
              setTimeout(() => { setStep(3); setStepFeedback(null); }, 1500);
            } else {
              handleMistake('Remember, Addition & Subtraction are opposites, as are Multiplication & Division.');
            }
          };

          const handleActionChoice = (choice) => {
            if (strikes >= 3) return;
            const expectedAction = `${getInverseOp(equation.op)}_${equation.term}`;
            if (choice === expectedAction) {
              setStepFeedback({ type: 'success', text: 'Exactly! Whatever we do to one side, we do to the other.' });
              setTimeout(() => { setStep(4); setStepFeedback(null); }, 1500);
            } else {
              handleMistake('Think about using the inverse operation with the term next to the variable.');
            }
          };

          const handleSolveSubmit = (e) => {
            e.preventDefault();
            if (strikes >= 3) return;
            const numericAns = parseInt(solveInput, 10);
            
            if (numericAns === equation.answer) {
              setStepFeedback({ type: 'success', text: `Brilliant! ${equation.variable} = ${equation.answer}` });
              
              const perfect = isPerfectQuestion;
              setStats(prev => {
                const newStreak = perfect ? prev.currentStreak + 1 : 0;
                const newScore = prev.score + (perfect ? 100 + (newStreak * 10) : 50);
                return {
                  ...prev,
                  correct: perfect ? prev.correct + 1 : prev.correct,
                  currentStreak: newStreak,
                  maxStreak: Math.max(prev.maxStreak, newStreak),
                  score: newScore
                };
              });

              setTimeout(() => generateEquation(), 2000);
            } else {
              handleMistake('Not quite. Check your math and try again!');
            }
          };

          const saveScore = async () => {
            if (stats.score === 0 || !playerName) return;

            const cleanName = filterName(playerName);

            if (!isFirebaseConfigured) {
              // Local Fallback if Firebase isn't set up yet
              setLeaderboard(prev => {
                const updated = [...prev, { id: Date.now(), name: cleanName, score: stats.score }];
                updated.sort((a, b) => b.score - a.score);
                return updated.slice(0, 50);
              });
              setGameState('leaderboard');
              return;
            }

            try {
              const lbCollection = db.collection('artifacts').doc('isolate-it-game').collection('public').doc('data').collection('leaderboard');
              await lbCollection.add({
                userId: user.uid,
                name: cleanName,
                score: stats.score,
                correctAnswers: stats.correct,
                maxStreak: stats.maxStreak,
                createdAt: firebase.firestore.FieldValue.serverTimestamp()
              });
              setGameState('leaderboard');
            } catch (err) {
              console.error("Failed to save score:", err);
            }
          };

          const percentCorrect = stats.total === 0 ? 0 : Math.round((stats.correct / (stats.total === 1 ? 1 : stats.total - (step < 4 ? 1 : 0))) * 100) || 0;

          const handleTeacherLogin = (e) => {
            e.preventDefault();
            if (passwordInput === 'Msulaw#1') {
                setPasswordPrompt(false);
                setPasswordInput('');
                setPasswordError(false);
                setGameState('teacher');
            } else {
                setPasswordError(true);
            }
          };

          const requestSort = (key) => {
            let direction = 'desc';
            if (sortConfig.key === key && sortConfig.direction === 'desc') {
              direction = 'asc';
            }
            setSortConfig({ key, direction });
          };

          const sortedLeaderboard = [...leaderboard].sort((a, b) => {
            let valA = a[sortConfig.key] || 0;
            let valB = b[sortConfig.key] || 0;
            
            // Handle string comparison for names
            if (typeof valA === 'string') valA = valA.toLowerCase();
            if (typeof valB === 'string') valB = valB.toLowerCase();

            if (valA < valB) return sortConfig.direction === 'asc' ? -1 : 1;
            if (valA > valB) return sortConfig.direction === 'asc' ? 1 : -1;
            return 0;
          });

          const renderProgressBar = () => (
            <div className="w-full bg-gray-200 rounded-full h-2.5 mb-6 overflow-hidden">
              <div 
                className="bg-blue-600 h-2.5 rounded-full transition-all duration-500 ease-out" 
                style={{ width: `${(step / 4) * 100}%` }}
              ></div>
            </div>
          );

          return (
            <div className="min-h-screen bg-slate-50 text-slate-900 font-sans flex flex-col items-center">
              {/* Header Bar */}
              <header className="w-full bg-white shadow-sm p-4 flex justify-between items-center max-w-4xl mx-auto rounded-b-xl">
                <div className="flex items-center gap-2 text-blue-600 font-bold text-xl">
                  <IconRotateCcw className="w-6 h-6" />
                  <span>Isolate It!</span>
                </div>
                {gameState === 'playing' && (
                  <div className="flex gap-4 sm:gap-6 text-sm font-semibold">
                    <div className="flex items-center gap-1 text-red-500" title="Strikes">
                      {[1, 2, 3].map((strikeNum) => (
                        <IconXCircle key={strikeNum} className={`w-5 h-5 ${strikeNum <= strikes ? 'fill-red-500 text-white' : 'opacity-30 text-gray-400'}`} />
                      ))}
                    </div>
                    <div className="flex items-center gap-1 text-orange-500">
                      <IconFlame className="w-5 h-5" /> Streak: {stats.currentStreak}
                    </div>
                    <div className="flex items-center gap-1 text-green-600 hidden sm:flex">
                      <IconTarget className="w-5 h-5" /> {percentCorrect}% Correct
                    </div>
                    <div className="flex items-center gap-1 text-indigo-600">
                      <IconTrophy className="w-5 h-5" /> {stats.score}
                    </div>
                    <button onClick={() => setGameState('gameover')} className="text-gray-500 hover:text-indigo-600 transition-colors ml-2 font-bold underline">
                      Stop & Save
                    </button>
                  </div>
                )}
              </header>

              <main className="flex-1 w-full max-w-2xl mx-auto p-4 flex flex-col justify-center">
                
                {/* === MENU STATE === */}
                {gameState === 'menu' && (
                  <div className="bg-white rounded-2xl shadow-xl p-8 text-center space-y-8 border-t-4 border-blue-500">
                    <div>
                      <h1 className="text-4xl font-extrabold text-slate-800 tracking-tight mb-4">Master the Inverse</h1>
                      <p className="text-slate-500 max-w-md mx-auto text-lg">
                        Learn how to solve algebraic equations by finding the operation, using its inverse, and isolating the variable.
                      </p>
                    </div>
                    
                    <div className="grid grid-cols-2 gap-4 text-left max-w-sm mx-auto bg-slate-50 p-4 rounded-xl border border-slate-100">
                      <div className="flex items-center gap-2"><div className="w-2 h-2 rounded-full bg-blue-500"></div> Addition</div>
                      <div className="flex items-center gap-2"><div className="w-2 h-2 rounded-full bg-red-500"></div> Subtraction</div>
                      <div className="flex items-center gap-2"><div className="w-2 h-2 rounded-full bg-green-500"></div> Multiplication</div>
                      <div className="flex items-center gap-2"><div className="w-2 h-2 rounded-full bg-purple-500"></div> Division</div>
                    </div>

                    <div className="max-w-sm mx-auto pt-2">
                      <label className="block text-sm font-bold text-slate-700 mb-2 text-left">Student Name</label>
                      <input 
                        type="text" 
                        value={playerName}
                        onChange={(e) => setPlayerName(e.target.value)}
                        maxLength={15}
                        placeholder="Enter your first name to play"
                        className="w-full p-3 border-2 border-slate-200 rounded-xl focus:border-blue-500 focus:outline-none text-center font-bold text-lg"
                      />
                    </div>

                    <div className="flex flex-col sm:flex-row gap-4 justify-center pt-2">
                      <button 
                        onClick={startGame}
                        disabled={!playerName.trim()}
                        className="flex items-center justify-center gap-2 bg-blue-600 hover:bg-blue-700 disabled:bg-gray-300 disabled:cursor-not-allowed text-white font-bold py-3 px-8 rounded-full shadow-lg hover:shadow-xl transition-all active:scale-95"
                      >
                        <IconPlay className="w-5 h-5"/> Start Playing
                      </button>
                      <button 
                        onClick={() => setGameState('leaderboard')}
                        className="flex items-center justify-center gap-2 bg-white border-2 border-slate-200 hover:border-slate-300 text-slate-700 font-bold py-3 px-8 rounded-full shadow-sm hover:shadow-md transition-all active:scale-95"
                      >
                        <IconTrophy className="w-5 h-5 text-yellow-500" /> Leaderboard
                      </button>
                    </div>
                    
                    <div className="mt-8 pt-4 border-t border-slate-100">
                      <button 
                        onClick={() => setPasswordPrompt(true)}
                        className="text-sm font-bold text-slate-400 hover:text-slate-600 underline tracking-widest"
                      >
                        TEACHER
                      </button>
                    </div>
                  </div>
                )}

                {/* === PLAYING STATE === */}
                {gameState === 'playing' && equation && (
                  <div className="bg-white rounded-2xl shadow-lg p-6 sm:p-10 w-full transition-all">
                    {renderProgressBar()}
                    
                    <div className="text-center mb-8">
                      <div className="text-sm font-bold text-blue-500 tracking-wider uppercase mb-2">
                        Step {step} of 4
                      </div>
                      <div className="text-5xl sm:text-7xl font-black text-slate-800 font-mono tracking-widest my-8 p-6 bg-slate-50 rounded-xl border-2 border-slate-100 shadow-inner inline-block">
                        {equation.string}
                      </div>
                    </div>

                    <div className="min-h-[250px] flex flex-col justify-start">
                      
                      {step === 1 && (
                        <div className="animate-fade-in">
                          <h2 className="text-xl font-semibold mb-6 text-center">What math operation is happening to the variable in this equation?</h2>
                          <div className="grid grid-cols-2 gap-4">
                            {[
                              { label: 'Addition', val: 'add' },
                              { label: 'Subtraction', val: 'subtract' },
                              { label: 'Multiplication', val: 'multiply' },
                              { label: 'Division', val: 'divide' }
                            ].map((opt) => (
                              <button 
                                key={opt.val}
                                onClick={() => handleOpChoice(opt.val)}
                                className="p-4 border-2 border-slate-200 rounded-xl font-bold text-lg text-slate-600 hover:border-blue-500 hover:bg-blue-50 transition-all active:scale-95"
                              >
                                {opt.label}
                              </button>
                            ))}
                          </div>
                        </div>
                      )}

                      {step === 2 && (
                        <div className="animate-fade-in">
                          <h2 className="text-xl font-semibold mb-6 text-center">What is the <span className="underline decoration-blue-500 decoration-4">inverse</span> of { {add: 'Addition', subtract: 'Subtraction', multiply: 'Multiplication', divide: 'Division'}[equation.op] }?</h2>
                          <div className="grid grid-cols-2 gap-4">
                            {[
                              { label: 'Addition', val: 'add' },
                              { label: 'Subtraction', val: 'subtract' },
                              { label: 'Multiplication', val: 'multiply' },
                              { label: 'Division', val: 'divide' }
                            ].map((opt) => (
                              <button 
                                key={opt.val}
                                onClick={() => handleInverseChoice(opt.val)}
                                className="p-4 border-2 border-slate-200 rounded-xl font-bold text-lg text-slate-600 hover:border-blue-500 hover:bg-blue-50 transition-all active:scale-95"
                              >
                                {opt.label}
                              </button>
                            ))}
                          </div>
                        </div>
                      )}

                      {step === 3 && (
                        <div className="animate-fade-in">
                          <h2 className="text-lg sm:text-xl font-semibold mb-6 text-center leading-relaxed">
                            How do we use the inverse operation to move the term to the other side and <span className="text-blue-600 font-bold">isolate the variable</span>?
                          </h2>
                          <div className="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            {[
                              { label: `Add ${equation.term}`, val: `add_${equation.term}` },
                              { label: `Subtract ${equation.term}`, val: `subtract_${equation.term}` },
                              { label: `Multiply by ${equation.term}`, val: `multiply_${equation.term}` },
                              { label: `Divide by ${equation.term}`, val: `divide_${equation.term}` }
                            ].map((opt) => (
                              <button 
                                key={opt.val}
                                onClick={() => handleActionChoice(opt.val)}
                                className="p-4 border-2 border-slate-200 rounded-xl font-bold text-lg text-slate-600 hover:border-blue-500 hover:bg-blue-50 transition-all active:scale-95"
                              >
                                {opt.label}
                              </button>
                            ))}
                          </div>
                        </div>
                      )}

                      {step === 4 && (
                        <div className="animate-fade-in flex flex-col items-center">
                          <h2 className="text-xl font-semibold mb-6 text-center">
                            Great! We do that to <span className="underline decoration-orange-400 decoration-4">both sides</span> of the equal sign. <br/><br/>So what is the variable equal to?
                          </h2>
                          <form onSubmit={handleSolveSubmit} className="flex items-center gap-4 text-3xl font-mono">
                            <span className="font-bold">{equation.variable} =</span>
                            <input 
                              type="number" 
                              value={solveInput}
                              onChange={(e) => setSolveInput(e.target.value)}
                              className="w-24 p-3 border-4 border-blue-200 rounded-xl text-center focus:border-blue-500 focus:outline-none transition-colors"
                              placeholder="?"
                              autoFocus
                            />
                            <button 
                              type="submit"
                              disabled={!solveInput}
                              className="bg-green-500 hover:bg-green-600 disabled:bg-gray-300 text-white p-4 rounded-xl transition-colors shadow-sm active:scale-95"
                            >
                              <IconChevronRight className="w-8 h-8" />
                            </button>
                          </form>
                        </div>
                      )}
                    </div>

                    <div className="mt-6 h-12 flex justify-center items-center">
                      {stepFeedback && (
                        <div className={`flex items-center gap-2 font-bold px-4 py-2 rounded-full animate-bounce ${
                          stepFeedback.type === 'success' ? 'bg-green-100 text-green-700' : 'bg-red-100 text-red-700'
                        }`}>
                          {stepFeedback.type === 'success' ? <IconCheckCircle2 className="w-5 h-5"/> : <IconXCircle className="w-5 h-5"/>}
                          {stepFeedback.text}
                        </div>
                      )}
                    </div>

                  </div>
                )}

                {/* === GAME OVER STATE === */}
                {gameState === 'gameover' && (
                  <div className="bg-white rounded-2xl shadow-xl p-8 text-center max-w-md mx-auto w-full border-t-4 border-indigo-500">
                    <IconTrophy className="w-16 h-16 text-yellow-500 mx-auto mb-4" />
                    <h2 className="text-3xl font-bold mb-2">Practice Complete!</h2>
                    
                    <div className="bg-slate-50 rounded-xl p-4 my-6 space-y-3 border border-slate-100">
                      <div className="flex justify-between font-bold text-lg">
                        <span className="text-slate-500">Final Score:</span>
                        <span className="text-indigo-600">{stats.score}</span>
                      </div>
                      <div className="flex justify-between font-bold">
                        <span className="text-slate-500">Correct Equations:</span>
                        <span className="text-green-600">{stats.correct}</span>
                      </div>
                      <div className="flex justify-between font-bold">
                        <span className="text-slate-500">Highest Streak:</span>
                        <span className="text-orange-500 flex items-center gap-1"><IconFlame className="w-4 h-4"/>{stats.maxStreak}</span>
                      </div>
                    </div>

                    {stats.score > 0 ? (
                      <div className="space-y-4">
                        <p className="text-slate-600 font-medium mb-4">Great job, {playerName}! Save your score to the leaderboard.</p>
                        <button 
                          onClick={saveScore}
                          className="w-full bg-indigo-600 hover:bg-indigo-700 text-white font-bold py-3 rounded-xl shadow-md transition-colors active:scale-95"
                        >
                          Submit Score for {playerName}
                        </button>
                      </div>
                    ) : (
                      <p className="text-slate-500 mb-6 font-medium">Keep practicing to get on the leaderboard!</p>
                    )}

                    <button 
                      onClick={() => setGameState('menu')}
                      className="mt-4 flex items-center justify-center gap-2 w-full bg-white border-2 border-slate-200 text-slate-600 font-bold py-3 rounded-xl hover:bg-slate-50 transition-colors active:scale-95"
                    >
                      <IconHome className="w-5 h-5"/> Return to Menu
                    </button>
                  </div>
                )}

                {/* === LEADERBOARD STATE === */}
                {gameState === 'leaderboard' && (
                  <div className="bg-white rounded-2xl shadow-xl p-6 sm:p-8 w-full max-w-xl mx-auto border-t-4 border-yellow-400">
                    <div className="flex items-center justify-center gap-3 mb-8">
                      <IconTrophy className="w-8 h-8 text-yellow-500" />
                      <h2 className="text-3xl font-black text-slate-800 uppercase tracking-wider">High Scores</h2>
                    </div>

                    <div className="bg-slate-50 rounded-xl border border-slate-200 overflow-hidden mb-6">
                      <div className="grid grid-cols-12 gap-2 p-3 bg-slate-100 border-b border-slate-200 font-bold text-xs text-slate-500 uppercase tracking-wider">
                        <div className="col-span-2 text-center">Rank</div>
                        <div className="col-span-6">Student Name</div>
                        <div className="col-span-4 text-right pr-2">Score</div>
                      </div>
                      
                      <div className="max-h-[400px] overflow-y-auto">
                        {leaderboard.length === 0 ? (
                          <div className="p-8 text-center text-slate-400 font-medium italic">
                            No scores yet. Be the first!
                          </div>
                        ) : (
                          leaderboard.map((entry, idx) => (
                            <div key={entry.id} className="grid grid-cols-12 gap-2 p-3 border-b border-slate-100 last:border-0 hover:bg-white transition-colors items-center">
                              <div className="col-span-2 text-center font-black text-slate-400">
                                {idx === 0 ? <span className="text-yellow-500 text-lg">1</span> : 
                                 idx === 1 ? <span className="text-slate-400 text-lg">2</span> : 
                                 idx === 2 ? <span className="text-amber-600 text-lg">3</span> : idx + 1}
                              </div>
                              <div className="col-span-6 font-bold text-slate-700 truncate">{entry.name}</div>
                              <div className="col-span-4 text-right pr-2 font-mono font-bold text-indigo-600">
                                {entry.score.toLocaleString()}
                              </div>
                            </div>
                          ))
                        )}
                      </div>
                    </div>

                    <button 
                      onClick={() => setGameState('menu')}
                      className="flex items-center justify-center gap-2 w-full bg-slate-800 hover:bg-slate-900 text-white font-bold py-4 rounded-xl shadow-md transition-all active:scale-95"
                    >
                      <IconHome className="w-5 h-5"/> Main Menu
                    </button>
                  </div>
                )}

                {/* === TEACHER DASHBOARD STATE === */}
                {gameState === 'teacher' && (
                  <div className="bg-white rounded-2xl shadow-xl p-6 w-full max-w-3xl mx-auto border-t-4 border-emerald-500">
                    <div className="flex items-center justify-between mb-8">
                      <div className="flex items-center gap-3">
                        <IconTarget className="w-8 h-8 text-emerald-500" />
                        <h2 className="text-3xl font-black text-slate-800 uppercase tracking-wider">Teacher Dashboard</h2>
                      </div>
                      <button 
                        onClick={() => setGameState('menu')}
                        className="text-sm font-bold bg-slate-100 hover:bg-slate-200 text-slate-600 py-2 px-4 rounded-lg transition-colors"
                      >
                        Log Out
                      </button>
                    </div>

                    <div className="bg-slate-50 rounded-xl border border-slate-200 overflow-hidden mb-6">
                      <div className="grid grid-cols-12 gap-2 p-3 bg-slate-100 border-b border-slate-200 font-bold text-xs text-slate-600 uppercase tracking-wider">
                        <div className="col-span-1 text-center">Rank</div>
                        <div className="col-span-4 cursor-pointer hover:text-emerald-600 transition-colors flex items-center gap-1 select-none" onClick={() => requestSort('name')}>
                          Student Name {sortConfig.key === 'name' && (sortConfig.direction === 'asc' ? '↑' : '↓')}
                        </div>
                        <div className="col-span-3 cursor-pointer hover:text-emerald-600 transition-colors flex items-center gap-1 select-none" onClick={() => requestSort('score')}>
                          Score {sortConfig.key === 'score' && (sortConfig.direction === 'asc' ? '↑' : '↓')}
                        </div>
                        <div className="col-span-2 text-center cursor-pointer hover:text-emerald-600 transition-colors select-none" onClick={() => requestSort('correctAnswers')}>
                          Correct {sortConfig.key === 'correctAnswers' && (sortConfig.direction === 'asc' ? '↑' : '↓')}
                        </div>
                        <div className="col-span-2 text-center cursor-pointer hover:text-emerald-600 transition-colors select-none" onClick={() => requestSort('maxStreak')}>
                          Streak {sortConfig.key === 'maxStreak' && (sortConfig.direction === 'asc' ? '↑' : '↓')}
                        </div>
                      </div>
                      
                      <div className="max-h-[500px] overflow-y-auto">
                        {sortedLeaderboard.length === 0 ? (
                          <div className="p-8 text-center text-slate-400 font-medium italic">
                            No student scores recorded yet.
                          </div>
                        ) : (
                          sortedLeaderboard.map((entry, idx) => (
                            <div key={entry.id} className="grid grid-cols-12 gap-2 p-3 border-b border-slate-100 last:border-0 hover:bg-white transition-colors items-center text-sm">
                              <div className="col-span-1 text-center font-bold text-slate-400">{idx + 1}</div>
                              <div className="col-span-4 font-bold text-slate-700 truncate">{entry.name}</div>
                              <div className="col-span-3 font-mono font-bold text-indigo-600">{entry.score?.toLocaleString() || 0}</div>
                              <div className="col-span-2 text-center font-medium text-green-600">{entry.correctAnswers || 0}</div>
                              <div className="col-span-2 text-center font-medium text-orange-500">{entry.maxStreak || 0}</div>
                            </div>
                          ))
                        )}
                      </div>
                    </div>
                  </div>
                )}

                {/* Password Modal for Teacher */}
                {passwordPrompt && (
                  <div className="fixed inset-0 bg-slate-900/50 backdrop-blur-sm flex justify-center items-center p-4 z-50">
                    <div className="bg-white rounded-2xl shadow-2xl p-6 w-full max-w-sm animate-fade-in">
                      <h3 className="text-xl font-bold text-slate-800 mb-4 flex items-center gap-2">
                        <IconTarget className="w-6 h-6 text-emerald-500" /> Teacher Access
                      </h3>
                      <form onSubmit={handleTeacherLogin}>
                        <input 
                          type="password" 
                          value={passwordInput}
                          onChange={(e) => {
                            setPasswordInput(e.target.value);
                            setPasswordError(false);
                          }}
                          placeholder="Enter Password"
                          className="w-full p-3 border-2 border-slate-200 rounded-xl focus:border-emerald-500 focus:outline-none mb-2"
                          autoFocus
                        />
                        {passwordError && <p className="text-red-500 text-sm font-bold mb-3">Incorrect password.</p>}
                        <div className="flex gap-2 mt-4">
                          <button 
                            type="button"
                            onClick={() => { setPasswordPrompt(false); setPasswordInput(''); setPasswordError(false); }}
                            className="flex-1 bg-slate-100 hover:bg-slate-200 text-slate-700 font-bold py-2 rounded-xl transition-colors"
                          >
                            Cancel
                          </button>
                          <button 
                            type="submit"
                            className="flex-1 bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-2 rounded-xl transition-colors"
                          >
                            Login
                          </button>
                        </div>
                      </form>
                    </div>
                  </div>
                )}

              </main>
              
              <style dangerouslySetInnerHTML={{__html: `
                .animate-fade-in { animation: fadeIn 0.4s ease-out forwards; }
                @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }
                input[type="number"]::-webkit-inner-spin-button, input[type="number"]::-webkit-outer-spin-button { -webkit-appearance: none; margin: 0; }
                input[type="number"] { -moz-appearance: textfield; }
              `}} />
            </div>
          );
        }

        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(<App />);
    </script>
</body>
</html>
