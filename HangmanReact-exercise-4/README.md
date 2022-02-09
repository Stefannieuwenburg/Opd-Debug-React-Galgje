Fix bug in AppContainer.js guessLetterHandler 

bug not good:

guessLetterHandler = event => {
    const newGuessedLetters = [...this.state.guessedLetters];
    newGuessedLetters.push(this.state.currentChosenLetter);
    this.setState({
      guessedLetters: newGuessedLetters,
      currentChosenLetter: ""
    });
    event.preventDefault();
  };

  it have to be:
  
  guessLetterHandler = event => {
    const inputGiven = this.state.currentChosenLetter.length > 0;
    const newLetter = !this.state.guessedLetters.includes(
      this.state.currentChosenLetter
    );
    if (inputGiven && newLetter) {
      const newGuessedLetters = [...this.state.guessedLetters];
      newGuessedLetters.push(this.state.currentChosenLetter);
      this.setState({
        guessedLetters: newGuessedLetters
      });
    }
    this.setState({ currentChosenLetter: "" });
    event.preventDefault();
  };
