# 📝Definition
You can embed notions of color and two-dimensional positions, etc. in a one-dimensional stream of characters. That’s what layout (typesetting, “markup”) languages such as Troff, [[TeX]], Word, [[HTML]], and [[XML]] (and  their  associated  graphical packages do). The point is that you can express layout  notions  in  plain  text,  but  the  connection  between  the  characters  written  and what appears on the screen is indirect, governed by a program that interprets those “markup” commands.
# ⌨Code
  ``` xml
  <hr>
  <h2>Organization</h2>
  This list is organized in three parts:
  <ul>
    <li><b>Proposals</b>, numbered EPddd, . . .</li>
    <li><b>Issues</b>, numbered EIddd, . . .</li>
    <li><b>Suggestions</b>, numbered ESddd, . . .</li>
  </ul>
  <p>We try to . . .<p>
  ```
# 🧠Intuition
The one-dimensional info to two-dimensional info thinking is really impressive!! The aim from a programming point of view is a direct correspondence between the objects in memory and the images on the screen.