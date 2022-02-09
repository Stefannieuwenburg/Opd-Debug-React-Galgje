Fix bug in App.js line 18 missing exclamation mark //guessedLetters.includes(letter) solution let remaining = word.filter(letter => !guessedLetters.includes(letter));
  return remaining.length === 0;
