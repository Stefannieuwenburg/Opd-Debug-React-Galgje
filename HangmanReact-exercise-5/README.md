Fix bug in App.js isGameOver line 30 greater than or equal

Bug not good:

const isGameOver = game => {
  if (wordGuessed(game.chosenWord, game.guessedLetters)) {
    return true;
  }
  if (
    getWrongLetters(game.chosenWord, game.guessedLetters).length >
    game.maxGuesses
  ) {
    return true;
  }
  return false;
};
bug fix: 

const isGameOver = (game, wrongLetters, wordWasGuessed) =>
  wordWasGuessed || wrongLetters.length >= game.maxGuesses;
