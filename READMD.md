class Text{
    @Text
    void shouldReturnBlack()
    {
        Dezhou dezhou = new dezhou();
        char expectedResult = scanf(Black: `2H 3H 5H 9H KH` White: `2C 3H 4S 5C 6H`);
        Assertions.assertequals(excepted:Black win,expectedResult);
    }
    @Text
    void shouldReturnWhite()
    {
       Dezhou dezhou = new dezhou();
       char expectedResult = scanf(Black: `2H 4S 4C 2D 4H` White: `2S 8S AS QS 3S`);
       Assertions.assertequals(excepted:White win,expectedResult);
    }
    void shouldReturnTie()
    {
       Dezhou dezhou = new dezhou();
       char expectedResult = scanf(Black: `2H 3D 5S 9C KD` White: `2D 3H 5C 9S KH`);
       Assertions.assertequals(excepted:Tie,expectedResult);
    }
}