# note
sounds are being used but aren't provided, if you want sound output you need to bring your own sounds and then create sounds.dat using the packer provided by nvgt
# coding style.
there are rules that if you want to read or contribute to this project that you need to be aware of.
1. Files need to be organized with includes, multiple directories with subdirectories depending on what their use is, as an example, menu.nvgt and dialog.nvgt go in includes/ui, this makes navigating the project much more easier for everyone.
2. Include what you use, even if it will be in scope anyway, even if game.nvgt is included somewhere and the compiler will not complain about something not being found, putting #include "Game.nvgt" tells me clearly what functions/classes/variables you're using in your script.
3. Avoid global variables and global functions, sometimes global variables and global functions are necessary which is acceptable but using them for every situation will result in unclear code and hard to maintain code in general, avoid it.
4. Name variables clearly, just because s is a sound object doesn't mean that it's useful, what is s used for, where did it come from? Can I search for it using a file editor or because it's 1 character that exists everywhere it's impossible to find? Is it easy to remember and makes sense in the context? As an example audio_game game(); makes sense as a variable, but audio_game g(); or audio_game ag(); does not, neither does agm, gm, ga, etc. This also applies for include names, use dialog.nvgt instead of dlg.nvgt, sound_dialog.nvgt instead of dlsound.nvgt.
5. In constructors with arguments that set members use the exact same naming as the member, and use this.member to set it, for example, if I have a class with a variable inside called name and I have the constructor that sets the name, it should be like my_class(int name) { this.name = name; }
6. Use snake case naming style, snake case naming is when you have an identifier, example variable name, function name, class name that has multiple words and you seperate them with underscores, that's called snake case naming, so instead of doing string soundfilename; or string soundFileName;, do string sound_file_name;
7. Use 4 space indentation, some people prefer tabs but I personally prefer spaces because they are more generalized.
8. Don't put 2 statements in one line, instead of doing if (my_array.is_empty()) return; do ```nvgt
if (my_array.is_empty()) {
    return;
}
```
9. If you're checking if a string or an array has no elements use .is_empty() instead of .length() == 0, this is more efficient.