const App = props => {
  const game = props.game;
  const wordWasGuessed = wordGuessed(game.chosenWord, game.guessedLetters);
  const wrongLetters = getWrongLetters(game.chosenWord, game.guessedLetters);
  const gameIsOver = isGameOver(game, wrongLetters, wordWasGuessed);

  const gameOver = gameIsOver ? (
    <GameOver chosenWord={game.chosenWord} wordGuesed={wordWasGuessed} />
  ) : null;

naam verkeerd in wordGuesed lijn 31.