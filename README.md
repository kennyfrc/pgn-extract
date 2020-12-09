## About

This is a mirror of [David J. Barnes' pgn-extract](https://www.cs.kent.ac.uk/people/staff/djb/pgn-extract/).

## Change History

*   22nd Apr 2019: Improved --repetition so that it does not give false positives when castling rights or who is to move are different.

    Retain next move number rather than resetting to 1 with --dropply and --dropbefore.

*   14th Apr 2019: Fixed a memory error in v18-10 that occurred when a positional match was found but the moves of the game were invalid.
*   28th Mar 2019: Added --xroster to suppress tags that are not required with -R.
*   13th Nov 2018: Missing SetUp tags no longer elicit an error message as this contravention of the standard is so common.
*   28th Oct 2018: Negative value accepted with --dropply to indicates plies to be retained at the end of the game.
*   18th Oct 2018: open game files in binary mode to cope with the Ctrl characters that appear in some.
*   17th Oct 2018: Accept Z0 as an alternative to --.
*   13th Oct 2018: Added --dropbefore as a result of a suggestion by Josip Salai. Fixed missing SetUp tag with --dropply. Fixed -H to work with 32-bit Windows.
*   7th Oct 2018: Added -y.
*   19th Aug 2018: Fixed a memory leak with -z.
*   11th July 2018: Added the MatchLabel tag and FENPatternI matching with -t after a suggestion by Hedinn Steingrimsson. In addition, significantly improved the efficiency of FENPattern matches.
*   3rd July 2018: Added the MaterialMatch tag with -z after a suggestion by Hedinn Steingrimsson.
*   23rd Apr 2018: With -R, include tags in the output that are not explicitly listed in the roster order. This aligns the behaviour with the documentation.
*   9th Feb 2018: Suppress warning for null moves when --allownullmoves is used. With --fixresulttags, prefer the terminating result if either it or the result tag is "*".
*   29th Dec 2017: Corrected failure to OR rather than AND the pseudo Elo tag used with -t.
*   17th Dec 2017: Accepted multiple NAG comment pairs after a move. If NAGs are suppressed then the associated comments are retained.
*   30th Nov 2017: Added --nestedcomments.
*   12th Nov 2017: Added --dropply after a suggestion by Heiko Bruns.
*   5th Oct 2017: Only require "960" in Variant tag strings for Chess960 games.
*   23rd Sep 2017: Added the previously documented, but unimplemented --underpromotion.
*   3rd Sep 2017: Bug fix for zero-move games which were not being followed by a blank line.
*   26th July 2017: --matchplylimit added following a suggestion by James Ward.
*   23rd July 2017: Bug fix for --splitvariants.
*   21st July 2017: Added --nobadresults to suppress games with inconsistent result indications. Fixed failure to correct terminating result with --fixresulttags. Added --allownullmoves.
*   15th July 2017: Added -Tf for FEN pattern matching.
*   8th July 2017: Added --plycount. With -z, use a FEN tag (if present) to count the number of pieces.
*   6th July 2017: Adjusted -z to work correctly with a position stability value of 0. Implemented the suggestion of Josip Salai that that FEN as the marker with --markmatches should be interpreted as a request to output the FEN encoding of the match position.
*   28th June 2017: Added a c1 comment to -Wepd output to record the game's result. Added the requirement that the Variant tag contain the string "chess 960" to be considered as Chess960 games on output. This primarily affects encoding of castling moves in long-algebraic notation.
*   6th June 2017: Added a second number to the -# flag to control file numbering.
*   4th June 2017: Chess960 long algebraic castling notation accommodated on both input and output. This is where castling is indicated by specifying the Rook's column as the destination for the King.
*   2nd June 2017: With --fixresulttags don't report inconsistent results that can be fixed.
*   21st May 2017: Added --commentlines after a suggestion by Gabriele Battaglia.
*   21st April 2017: Optional limiting depth added to --splitvariants.
*   7th April 2017: License updated to version 3 of the GPL.
*   31st March 2017: Added --splitvariants after a suggestion by Vladimir Volovich to add functionality found in pgnsplit.
*   19th February 2017: Extended --selectonly and added --skipmatching after a suggestion by Folkert van Heusden.
*   16th February 2017: Fixed runtime failure when -x and -n were used together. Added missing SetUp tag when a FEN tag is present. Correct "1/2" in a Result tag to "1/2-1/2". Added explicit Q promotion when unspecified. Fixed lack of output with -W (i.e., output as source).
*   29th January 2017: Added --hashcomments to add a comment containing a polyglot hash code after each move. Added -H for Zobrist polyglot hash matches.
*   Added text after -F for FEN-position output at arbitrary positions and not simply at the end of a game. Suggested by Josip Salai.
*   22nd January 2017: Added --stopafter.
*   20th January 2017: Added --nosetuptags and --onlysetuptags following a discussion with Mike Crockett. Added -p[elu] for finer control of game length matching than provided by -b.
*   14th January 2017: Fixed --fuzzydepth.
*   9th January 2017: Improved the efficiency of (lack of) stalemate detection.
*   1st January 2017: Added --fixresulttags for conflicts between the game termination and the result tag. Source code rewrites of function names for more consistent naming.
*   8th November 2016: Allows 'b' as a trailing promotion character, previously disallowed.
*   3rd September 2016: Added --quiescent for position quiescence after a suggestion from Mike Crockett.
*   17th April 2016: Added --tagsubstr for substring matches on tags.
*   4th March 2016: Added --quiet to suppress the number of games processed, as an extension of -s. (Suggested by Norm Pollock.)
*   21st November 2015: Added recognition of Chess960 FEN encodings and application of its castling rules.
*   16th October 2015: Added --fifty, --repetition, and warnings about inconsistent results in tags on checkmate and stalemate after suggestions by Norm Pollock.
*   6th May 2015: Fixed errors in the half-move clock on castling and pawn promotion, thanks to Brandon RichardWebster.
*   23rd Mar 2015: Added --nofauxep after a suggestion by Norm Pollock.
*   21st Mar 2015: Fixed off-by-one in move number output with -F when white-to-move.
*   20th Mar 2015: Added -Wxlalg at the suggestion of Bruce Ramsey.
*   8th Jan 2015: Fixed bug in game counting with -#. Suppressed games with null moves (--) in the main line.
*   28th October 2014\. Added --selectonly after a suggestion by Francis Steen.
*   2nd September 2014\. Corrected an error in the generation of hashcodes when a promotion is made.
*   31st May 2014\. Added --addhashcode.
*   25th May 2014\. Added --totalplycount for Erich Körber.
*   5th March 2014\. Added --keepbroken to allow broken games to be output. Added at the request of Mark Crowther primarily to deal with the problem of live recording where the kings are moved to the centre of the board at the end of a game and erroneously included in the score.
*   6th September 2013\. Corrected failure to 'or' together multiple dates with -T and -t.
*   16th May 2013\. Corrected an error in the whole-move number in FEN output, thanks to Vincent Fleuranceau.
*   14th May 2013\. Null move notation (--) in variations recognised.
*   16th April 2013\. Added --fuzzydepth. This is due to Owen D. Lyne who requested this functionality years ago - sorry for taking so long, Owen!
*   11th April 2013\. Added -Wuci.
*   29th March 2013\. Added --version.
*   26th March 2013\. Fixed crash when a string to be output is longer than the output line length.
*   12th March 2013\. Added long-form versions of -a, -c, -d and -o: --append, --checkfile, --duplicates and --output.
*   9th February 2013\. Added pattern matching based on FEN descriptions and --markmatches for JS.
*   23rd December 2012\. Added --fencomments for Tyler Eaves.
*   2nd December 2012\. Allowed 0 for --plylimit.
*   22nd September 2008\. Added --stalemate for Wieland Belka.
*   15th September 2008\. Added --nochecks and fixed -A so that it handles long-form arguments properly.
*   22nd December 2007\. Added --notags, --plylimit, --nomovenumbers and --noresults after a suggestion by Wieland Belka to be able to create opening books.

*   24th April 2007\. Fixed a bug with mate annotation. Added the -M flag for checkmate matches, which is due to Richard Jones.
*   19th October 2005\. Added language-specific letters to -Welalg following a suggestion from Folkert van Heusden.
*   1st May 2004: Fixed an error with ECO classification that was causing the file list to be out of sync.
*   29th April 2004: Buffered game text before outputting it, so that trailing spaces on lines (which violate the PGN spec) can be deleted.  
    Games with zero moves are now acceptable.
*   26th April 2004: Slight modification to one of the hashing values made in order to try to avoid clashes in ECO matches. ECO matches now have a discretion of up to 6 half moves.
*   13th February 2002: Added -Welalg as an output format following a suggestion from Rafal Furdzik.
*   27th March 2001
    *   Added output of EPD via -Wepd.
    *   Fixed a long standing error in FEN castling rights. These were not being withdrawn if a Rook was captured on its home square. Pointed out by Karl-Martin Skontorp, who also provided the incentive to add -Wepd.
*   26th April 2000 Added the -R flag for tag ordering.
*   22nd April 2000 Completed implementation of -A to work with all flags.
*   21st April 2000
    *   Added the -F flag.
    *   Added support for reading Russian source files.
*   11th April 2000
    *   Added the -A flag.
    *   Extended usage of -Wsan to support output in different languages.
    *   Usage of -e with -7 retains an ECO tag in matched games.
    *   FEN tags with the -t flag are used as positional matches (equivalent to -x matches).
    *   Non-standard tags are now retained in game output.
*   12th January 2000 C compiler with Red Hat Linux 6 was no longer happy with static initialisations involving stdin, stdout and stderr. Changes made to lex.c and main.c to work around this. Pointed out by Mladen Bestvina.
*   18th October 1999 Numbers greater than 3 allowed with -E, at the request of Owen Lyne.
*   15th December 1997 Treat \r as WHITESPACE (for DOS files).
*   8th June 1997 Added -b flag to set bounds on the number of moves in a game to be matched.
*   2nd May 1997 Corrected small error when strings were not terminated properly. In tags, this resulted in the corrected tag ending in ]"] instead of "].
*   17th February 1997 Added a little more error recovery.
*   15th November 1996 Added -Z.
*   23rd Sep 1996 It is no longer necessary to omit move numbers from the variations files (-v and -x). This makes it easier to cut and paste games of interest into these files.
*   28th Jun 1996 It is no longer necessary to terminate the tag file (-t). Relational operators added in the tag file (-t). Added -E flag.
*   7th May 1996 Corrected failure to make ECO classification when combined with -x. Added lalg and halg as long algebraic output formats.
*   9th Oct 1995 Add -#
*   25th Sep 1995: Default to reading stdin if no file arguments are provided.
*   24th Jul 1995: Added setup from FEN tags.
*   18th Jul 1995:
    *   Added material balance matches with -z.
    *   Added 'L' as a minor piece letter in ending files.
*   14th Jul 1995: Made the order of arguments immaterial.
*   5th Jul 1995:
    *   Added ECO classification with -e.
    *   Fixed false partial substring matches with -v, e.g. textual variation move Nc6 is now no longer matched by game move c6.
*   22nd Mar 1995: Made permutation matching with -v the default and added -P to suppress it.
*   Jan 1995: Added -n and -L.
*   17th Nov 1994: Liberated the program from using YACC and Lex.
*   13th Oct 1994: Released test version with ChessMaster output.
*   20th Sep 1994: Added move rewriting and -W flag.
*   7th Sep 1994: Added -D flag.
*   6th Sep 1994: Added -C and -V flags and soundex matching.
*   5th Sep 1994:
    *   Integrated the positional variation code from a separately developed program.
    *   Added -N flag.
    *   Added ! to the textual variation syntax.
    *   Removed the writing to extract.pgn that was present in an earlier unreleased version.
    *   Added -d flag.
*   8th Jul 1994:
    *   Added -o flag.
    *   Discarded writing to standard output in DOS version because of extensive problems trying to make this work with redirected output. Instead, output is written to the file extract.pgn.
*   6th Jul 1994: Added -7 flag.
*   9th May 1994: Added -p flag for variation permutations.
*   6th May 1994: Added * as a don't-care move in variations files.
*   26th Apr 1994: Added the -t flag for files of extraction criteria.
*   25th Apr 1994: Added the -T flag for extraction criteria.
*   22nd Apr 1994: Added the -f flag for handling lists of PGN files.
*   13th Apr 1994:
    *   Cleaned up the game-length determination by reading/writing files in binary-mode.
    *   Added -a flag for appending to existing .pgn files.
    *   Added multiple input files.
    *   Made verbose output the default behaviour.
