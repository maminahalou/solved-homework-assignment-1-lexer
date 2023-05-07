Download Link: https://assignmentchef.com/product/solved-homework-assignment-1-lexer
<br>
5/5 - (2 votes)

In this assignment, you are going to implement two versions of lexer for a small language, “miniJava”: one through manual implementation and the other with the lexer-generation tool, JavaCC. This assignment builds on top of Lab 2. If you have not attended Lab 2 for any reason, please go through its materials first.

PreparationDownload the zip file “hw1.zip” from D2L. After unzipping, you should see a hw1 directory with the following items:– hw1.pdf — this document– mjLexicalRules.pdf — miniJava’s lexical rulesThis document provides the base for the lexer implementation.– mjTokenConstants.java — suggested internal token code for the hand-written lexer– Lexer0.jj, Lexer0.java — sample starting versions for the two lexers– Makefile — for compiling the lexers(Usage: “make lexer1”, “make lexer2”, or just “make” for both)– runl1, runl2 — two scripts for running the tests(Usage: “./runl1 tst/*.txt”, “./runl2 tst/*.txt”)– tst/ — a set of test inputs (incomplete coverage)Your Tasks1. Implementing a lexer using JavaCC. (45 points)Name your JavaCC lexer program Lexer1.jj. Include the name Lexer1 as the package name inthe header section of the program (see Lexer0.jj):PARSER_BEGIN(Lexer1)public class Lexer1 {…}PARSER_END(Lexer1)2. Implementing a lexer manually. (45 points)Name your hand-written lexer Lexer2.java. You are free to organize this program in any way yousee fit, but here is a top-level structure used in Lab 2 lexer programs (see Lexer0.java):1public class Lexer2 implements mjTokenConstants {static class LexError extends Exception {int line;int column;…}static class Token {int kind; // token codeint line; // line number of token’s first charint column; // column number of token’s first charString lexeme; // lexeme string…}public static void main(String [] args) {…}}3. Developing four testing inputs. (10 points)The provided test inputs, testinput*.txt, cover only correct tokens. Your third task is to develop four new test inputs for testing the four types of lexical errors (see below). Name your filestesterror1.txt — testerror4.txt.RequirementsThe following are the common requirements for both the hand-written and the JavaCC-generated lexers.• Recognize all the tokens specified in the file, mjLexicalRules.pdf.• Display tokens from an input stream in the following format:– One token per line.– Each line starts with a pair (linNum,colNum), where the two numbers are the starting line and column numbers of the token. Then, for an ID token, display ID(lexeme);. for an INTLIT token, display INTLIT(lexeme’s value);(e.g. for the input sequence, 00123, the display should be INTLIT(123)). for an STRLIT token, display STRLIT(lexeme);. for any other token, display lexeme.– After all tokens are displayed, show one last line: Total: tknCnt tokens.Exact spacing among items within a line is not required.