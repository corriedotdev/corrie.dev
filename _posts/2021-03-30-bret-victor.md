---
layout: post
title: The Future of Programming & The Humane Representation of Thought 
excerpt: "This is more of a real time write up of two videos I have found from quite a special computer scientist Bret Victor. He is clearly passionate about interface design and has some incredibly interesting write ups looking into the past of interaction and the initial words mentioned in early literature that is used everyday now."
categories: [code]
comments: true
galleries:
 1:
   -
     - { url: '/img/spatial-1.PNG', alt: '1'}
     - { url: '/img/spatial-2.PNG', alt: '2'}
 2:
   -
     - { url: '/img/visual-1.PNG', alt: '1'}
 3:
   -
     - { url: '/img/small-talk.PNG', alt: '1'}
 4:
   -
     - { url: '/img/actor.PNG', alt: '1'}
---


# Foreword
This is more of a real time write up of two videos I have found from quite a special computer scientist Bret Victor. He is clearly passionate about interface design and has some incredibly interesting write ups looking into the past of interaction and the initial words mentioned in early literature that is used everyday now. I am unsure on his venture using paper and stickers to code with computer vision to complete tasks. As I haven't looked into it enough put simply.

What I can see this being is appended to current methods of visualizing. For example writing on a white board. There is some math being written out in real time and getting a calculator is slow.. lets just have a projector beam the answer onto the whiteboard so the math is already done. We wrote the completed formulas and the computer vision did the rest. Little things like this I can see having a high impact value on society, its cheap and affordable. I will admit though I am not too sure what Dynamicland really is.. I find it hard to believe that VR can't solve the same problem that is being described here. Why not find a more human and intuitive way of sharing ideas? Gestures? Real time communication and exchange of ideas real time with physical avatars or real time lidar scans. 
I don't know but I will find out. Enjoy the write up, I was essentially a scribe for the videos.

#  The Future of Programming
Initially when watching this presentation I just lacked the humour, I really have no idea what on earth the audience was laughing at I didn't find it funny, but more of a story of technology through time. Its not funny really, its amazing. Its fact how insane progress has been over the last 100 years. The wright brothers will always be a date to hold for comparison. 1903 We had our first flight, the development of the pump was 2000BC by the Egyptians, simply buckets on some string. You would be surprised the impact and influence on the world the pump had, it helped create the combustion engine and prior allowed bridges to be developed. [More here if curious on the history of the pump](https://www.pumpsandsystems.com/history-pumps-through-years)

The nature of adopting ideas leads into the brain of not adopting new ways of thinking, brains are slow but computers are fast. People need to adopt to new ideas. Lots of resistance to new ways of working, unlearning what you know and approaching a new technique. Such as going from machine code to SOAP (Assembly.) Soon after SOAP was replaced with FORTRAN. There is resistance to learning a new language or method of adopting new ideas.

## 4 Ideas Discussed
- Coding -> Direct Manipulation of Data
- Procedures -> goals and constraints
- Text Dump -> spatial representation (here is where I can forsee VR being used as another spatial representation)
- Sequential -> concurrent

The concept of drawing into code, markup languages and stylesheet will be dead as its all direct manipulation of some graphical representation. Expressing your program on what you want it to do, not how you do it. 
This reminds me of GPT-2 where demos have been shown with descriptions being provided and then the output is the working visual code. I would say that hooking up the arithmetic is harder, but visually I can see the concept working more for UI designers. Feed in constraints to GPT-2 and ask it for a simple menu with a button x, y. This is pattern matching. Sketchpads, constraints, pattern matching are providing high level goals to the computer to solve.

J.C.R Licklidar has a theory for the "intergalactic computer network." A web of all the computers linked together to fulfill tasks.

The concept of programs becoming satinet and communicating to fulfill a purpose is sexy however I cant imagine how it would work (yet.) Ideally just having json being the data that is being passed to the application layer of the services then I can see this working. Perhaps the services have automated test cases to fulfill before accepting and understanding the purpose of the other program. There is an intermediary step to accept and acknowledge the program being interfaced with is the correct one by automating test cases. 

# Figuring out procedure communication
If we present a calculator 1+1 we get 2, so lets present this data to services until we get 2. Edge case over to one plus one will fail, this program wont work due to int string (ignore generics for this example.) But finding an text to in program to use first, we can then get the desired output. This seems computationally complex and would be O^2 if we don't ever tell the system where to look for int to text or that it is a requirement, but with a global network of computers with immense computing power I could see it perhaps running through numerous program types to fulfill the purpose, obviously categorizing programs with expected ins and outs im just toying with the concept here. 

However the talk removes the thought of API's such as JSON in general and requires goals as the driving force behind exchange of data between systems.

## Spatial Representation of Information (My Research too)
- Text Dump -> Spatial Representation 

Punch cards are good for displaying text, tele-prompts,  all good for reading 'text dumps' but we now use monitors which have this other layer of spatial ability.

### NLS (Online System) 1968
How can we represent this dynamic information spatially. The context menu used in the presentation is looking at a drop down list and then visualized in a node linked tree mesh in a 2D diagram. Same information is being displayed in two ways.

{% include gallery.html  gallery=1 %}

Its an example of representing dynamic information spatially.

### GRAIL 1968

A system for programming using flow charts. Stylus on a tablet input device. On this note it is interesting as it looks like "blueprints" which is found in the Unreal Engine for programming using a node based interface for visual scripting. In Unity the equivalent was called Bolt but is now simply referred to as Unity Visual Scripting.

The special thing that surprises me for GRAIL is the input is entirely drawing by hand, not a node list that is generated but physically drawing onto the display. Hopefully better visualized below. This is assigning semantic meaning to the drawings that is being produced to script.

{% include gallery.html  gallery=2 %}

### Small Talk Browser
This sparked my attention. It appears to be an IDE with separation of concerns. For example the top left is the method definition moving down to class and functions in each class. The code is the section at the bottom, interesting take on the IDE, Unity have panels you can move around for different tools which I really enjoy using but the IDE is still visual studio. I tend to have as many windows (panels) open that displays as much information as possible so I can scan long classes with ease. Albeit long classes are bad by design but still.

{% include gallery.html  gallery=3 %}

Seems to be quite confident with his statement 
>  "in 40 years we won't be coding in text files. Right? We have been shown the way"

I feel the same about VR applications back in the 90's There are some interesting design concepts that are applicable today, even with the drastic change in technology. 


These are all ways of interacting with the computer in real time. Note the term real time. Interactive computing will require real time feedback for interacting with the interface.

### Parallel Programming
This is point 4. Sequential programming to concurrent. The bottle neck is the VON Neumann bottleneck where the CPU is linked up to a memory unit and the processor executes processes consecutively. The memory is mostly idle and not being used as each instruction is being picked out of memory to be executed. 

Massively parallel processor array is alluded to the future of architecture. Todays programming is completed by threads and locks but doesn't scale with numerous processors sharing memory for obvious reasons. 

Carl Hewlit came up with the concept of the "Actor Model." Its inspired by physics with particles each having their own state and interacting with their surroundings. Asynchronously doing their own thing and sending messages to each other.

Bret notes that we will need parallel programming hardware. I am uneducated on quantum computing and that is what I will be looking into next when I get some down time from XR Interaction design.

{% include gallery.html  gallery=4 %}


# Humane Representation of Thought

 
## Closing Thoughts


## Further Reading
Check out the following links for inspiration and further reading about this topic
* [The Future of Programming](https://www.youtube.com/watch?v=8pTEmbeENF4)
* [Humane Representation of Thought](https://www.youtube.com/watch?v=agOdP2Bmieg)
* [Dynamic Land](https://dynamicland.org/#mission)
* [Scale-free Networks are Rare](https://www.nature.com/articles/s41467-019-08746-5)
* [Computational Rationality](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.720.2764&rep=rep1&type=pdf)
* [Economic Reasoning and Artificial Intelligence](https://science.sciencemag.org/content/349/6245/267)
* If these look familiar then reach out.

<a href="#" id="emailclick" onclick="replace_email()">My Email</a>

<script>
var email;

function add_mailto() {
  const elem = document.getElementById("emailclick");
  elem.href = `mailto:${email}`;
}

function replace_email() {
  // spam prevention
  const domain = "cjgstudio.com";
  const name = [16, 28, 1, 1, 26, 22];
  const xor_with = 115;
  let constructed = "";
  name.forEach(function(i) {
    constructed += String.fromCharCode(i ^ xor_with);
  })
  email = `${constructed}@${domain}`;
  const elem = document.getElementById("emailclick");
  elem.text = email;
1
  window.setTimeout(add_mailto, 100);
}
</script>