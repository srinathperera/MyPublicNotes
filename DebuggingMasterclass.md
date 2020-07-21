# Book: The 9 Indispensable Rules for Finding Even the Most Elusive Software and Hardware Problems 

* said that the book gave them the right words to transmit their skills to other members of the team.
* Debugging usually means figuring out why a design doesn’t work as planned. Troubleshooting usually means figuring out what’s broken in a particular copy of a product when the product’s design is known to be good—there’s a deleted file,
    * Doctors troubleshoot the human body—they never got a chance to debug it.
    * Troubleshooting books, on the other hand, work only on a broken part. They boast dozens of tables, with symptoms, problems, and fixes for anything that might go wrong with a particular system.
    * But they don’t help much with new, unknown problems.
* The essence of “Understand the System” is, “Read the manual.” Contrary to my dad’s comment,
    * Programming guides and APIs can be very thick, but you have to dig in—the function that you assume you understand is the one that bites you.
    * Be like Einstein, who never remembered his own phone number. “Why bother?” he would ask. “It’s in the phone book.”
    * Getting it to fail while I watched was the key. This is typical of many debugging problems—you can’t see what’s going on because it doesn’t happen when it’s convenient to look at it.
* You have enough bugs already; don’t try to create new ones.
* Recreate 
    * There are three reasons for trying to make it fail: 
        * So you can look at
        * So you can focus on the cause.
        * So you can tell if you’ve fixed it. Once
    * When the failure sequence requires a lot of manual steps, it can be helpful to automate the process.
    * Simulating a bug by trying to re-create it on a similar system is more useful, within limits. If a bug can be re-created on more than one system, you can characterize it as a design bug—it’s not just the one system that’s broken in some way. Being able to re-create it on some configurations and not on others helps you
    * But if you don’t have the same equipment or the same conditions, and thus the software doesn’t fail, the temptation is to try to simulate the equipment or invent new test programs. Don’t do it—bite the bullet and either bring the equipment to your engineers or send an engineer to the equipment (with a taxi-load of instrumentation).
    * Hard to recreate bugs
        * If the problem is intermittent because the failure is caused by a low-likelihood event (such as a noise peak), then making the condition (the noise) more random increases the likelihood of these events.
        * Randomness makes proving that you fixed it a lot harder, of course.
        * If you use statistical testing, the more samples you run, the better off you are. But it’s far better to find a sequence of events that always goes with the failure—even if the sequence itself is intermittent, when it happens, you get 100 percent failure.
        * Find the uncontrolled condition that makes it intermittent. Vary everything you can—shake it, rattle it, roll it, and twist it until it shouts.
    * Make It Fail It seems easy, but if you don’t do it, debugging is hard. Do it again. Do it again so you can look at it, so you can focus on the cause, and so you can tell if you fixed it.
* Quit thinking and look.
    * Quit Thinking and Look “It is a capital mistake to theorize before one has data. Insensibly one begins to twist facts to suit theories, instead of theories to suit facts.” —SHERLOCK HOLMES, A SCANDAL IN BOHEMIA
    * And you’ll understand that the measure of a good debugger is not how soon you come up with a guess or how good your guesses are, but how few bad guesses you actually act on.
    * Quit Thinking and Look You can think up thousands of possible reasons for a failure. You can see only the actual cause.
    * You have to put instrumentation into or onto the system.
    * By looking at captured information, you can easily compare a bad run to a good one (see Rule 5: Change One Thing at a Time). If you capture the right information, you will be able to see some difference between a good case and a failure case.
    * but you should guess only to focus the search. You still have to confirm that your guess is correct by seeing the failure before you go about trying to fix the failure. In
    * “How often have I said to you that when you have eliminated the impossible, whatever remains, however improbable, must be the truth?” —SHERLOCK HOLMES, THE SIGN OF THE FOUR War Story.
    * Watch out for Heisenberg.
    * Narrow the search. Home in on the problem. Find the range of the target. The common technique used in any efficient target search is called successive approximation—you want to find something within a range of possibilities, so you start at one end of the range, then go halfway to the other end and see if you’re past it or not.
    * a major corruption is invisible? One way to make a subtle effect more obvious is to use a really easy-to-recognize input or test pattern.
    * Use easy-to-spot test patterns.
* Fix the bugs you know about. Bugs defend and hide one another. Take ’em out as soon as you find ’em.
    * Our software engineer made a change to try to fix the problem, but when it didn’t fix the problem, he assumed that it had no effect.
    * It’s more effective to remember to do something (“Grab the bar!”) than to remember not to do something (“Don’t touch that dial!”). So, grab the bar!
* Using two cases, one that failed and one that didn’t, compare scope traces, code traces, debug output, status windows, or whatever else you can instrument.
* Some cases are tricky, though. Sometimes the problem has existed for a long time, but it doesn’t show up until something else changes, like the timing or the database size.
* Change One Thing at a Time
    * Isolate the key factor. Don’t change the watering schedule if you’re looking for the effect of the sunlight. Grab the brass bar with both hands. If you try to fix the nuke without knowing what’s wrong first, you may have an underwater Chernobyl on your hands.
    * Compare it with a good one.
    * Determine what you changed since the last time it worked.
* “There is no branch of detective science which is so important and so much neglected as the art of tracing footsteps.”
    * Write Down What You Did, in What Order, and What Happened
    * Write down what you did, in what order, and what happened as a result. When did you last drink coffee? When did the headache start? Understand that any detail could be the important one.
    * Write it down!
* Question Your Assumptions
    * Ask yourself the age-old stupid question: “Is it plugged in?”
    * At some point when you run into a problem that seems completely otherworldly, stop and check to see that you’re actually on the right planet.
    * “Convictions are more dangerous enemies of truth than lies.” —FRIEDRICH NIETZSCHE
    * Check the Plug Obvious assumptions are often wrong. And to rub it in, assumption bugs are usually the easiest to fix.
* There are at least three reasons to ask for help,
    * a fresh view, expertise, and experience.
    * “Nothing clears up a case so much as stating it to another person.” —SHERLOCK HOLMES, SILVER BLAZE
    * And people are usually willing to help because it gives them a chance to demonstrate how clever they are.
    * In fact, sometimes explaining the problem to someone else gives you a fresh view,
    * Report Symptoms, Not Theories
    * why. This is worth presenting; the fact is, you found something you didn’t expect or don’t understand. It may not be relevant, but it is information.
* Don’t be proud. Bugs happen. Take pride in getting rid of them, not in getting rid of them by yourself.
