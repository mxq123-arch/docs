# Source: https://github.com/mintlify/docs/blob/main/snippets/color-generator.jsx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

 

## FilesExpand file tree

 main

/

# color-generator.jsx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

## History

[History](https://github.com/mintlify/docs/commits/main/snippets/color-generator.jsx)

History

110 lines (103 loc) · 3.87 KB

## FilesExpand file tree

 main

/

# color-generator.jsx

Copy path

Top

## File metadata and controls

- Code
 
- Blame
 

110 lines (103 loc) · 3.87 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/snippets/color-generator.jsx)

Copy raw file

Download raw file

Open symbols panel

Edit and raw actions

export const ColorGenerator = () => { const \[hue, setHue\] = useState(165) const \[saturation, setSaturation\] = useState(84) const \[lightness, setLightness\] = useState(31) const \[colors, setColors\] = useState(\[\]) useEffect(() => { const newColors = \[\] for (let i = 0; i < 5; i++) { const l = Math.max(10, Math.min(90, lightness - 20 + i \* 10)) newColors.push(\`hsl(${hue}, ${saturation}%, ${l}%)\`) } setColors(newColors) }, \[hue, saturation, lightness\]) const copyToClipboard = (color) => { navigator.clipboard .writeText(color) .then(() => { console.log(\`Copied ${color} to clipboard!\`) }) .catch((err) => { console.error("Failed to copy: ", err) }) } return ( <div className="p-4 border dark:border-white/10 rounded-2xl not-prose"> <div className="space-y-4"> <div className="space-y-2"> <label className="block text-sm text-zinc-950/70 dark:text-white/70"> Hue: {hue}° <input type="range" min="0" max="360" value={hue} onChange={(e) => setHue(Number.parseInt(e.target.value))} className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1" style={{ background: \`linear-gradient(to right, hsl(0, ${saturation}%, ${lightness}%), hsl(60, ${saturation}%, ${lightness}%), hsl(120, ${saturation}%, ${lightness}%), hsl(180, ${saturation}%, ${lightness}%), hsl(240, ${saturation}%, ${lightness}%), hsl(300, ${saturation}%, ${lightness}%), hsl(360, ${saturation}%, ${lightness}%))\`, }} /> </label> <label className="block text-sm text-zinc-950/70 dark:text-white/70"> Saturation: {saturation}% <input type="range" min="0" max="100" value={saturation} onChange={(e) => setSaturation(Number.parseInt(e.target.value))} className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1" style={{ background: \`linear-gradient(to right, hsl(${hue}, 0%, ${lightness}%), hsl(${hue}, 50%, ${lightness}%), hsl(${hue}, 100%, ${lightness}%))\`, }} /> </label> <label className="block text-sm text-zinc-950/70 dark:text-white/70"> Lightness: {lightness}% <input type="range" min="0" max="100" value={lightness} onChange={(e) => setLightness(Number.parseInt(e.target.value))} className="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1" style={{ background: \`linear-gradient(to right, hsl(${hue}, ${saturation}%, 0%), hsl(${hue}, ${saturation}%, 50%), hsl(${hue}, ${saturation}%, 100%))\`, }} /> </label> </div> <div className="flex space-x-2"> {colors.map((color, idx) => ( <div key={idx} className="h-16 rounded flex-1 cursor-pointer transition-transform hover:scale-105" style={{ backgroundColor: color }} title={\`Click to copy: ${color}\`} onClick={() => copyToClipboard(color)} /> ))} </div> <div className="text-sm font-mono text-zinc-950/70 dark:text-white/70"> <p> Base color: hsl({hue}, {saturation}%, {lightness}%) </p> </div> </div> </div> ) }

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

20

21

22

23

24

25

26

27

28

29

30

31

32

33

34

35

36

37

38

39

40

41

42

43

44

45

46

47

48

49

50

51

52

53

54

55

56

57

58

59

60

61

62

63

64

65

66

67

68

69

70

71

72

73

74

75

76

77

78

79

80

81

82

83

84

85

86

87

88

89

90

91

92

93

94

95

96

97

98

99

100

101

102

103

104

105

106

107

108

109

110

export const ColorGenerator \= () \=> {

const \[hue, setHue\] \= useState(165)

const \[saturation, setSaturation\] \= useState(84)

const \[lightness, setLightness\] \= useState(31)

const \[colors, setColors\] \= useState(\[\])

useEffect(() \=> {

const newColors \= \[\]

for (let i \= 0; i < 5; i++) {

const l \= Math.max(10, Math.min(90, lightness \- 20 + i \* 10))

newColors.push(\`hsl(${hue}, ${saturation}%, ${l}%)\`)

}

setColors(newColors)

}, \[hue, saturation, lightness\])

const copyToClipboard \= (color) \=> {

navigator.clipboard

.writeText(color)

.then(() \=> {

console.log(\`Copied ${color} to clipboard!\`)

})

.catch((err) \=> {

console.error("Failed to copy: ", err)

})

}

return (

<div className\="p-4 border dark:border-white/10 rounded-2xl not-prose"\>

<div className\="space-y-4"\>

<div className\="space-y-2"\>

<label className\="block text-sm text-zinc-950/70 dark:text-white/70"\>

Hue: {hue}°

<input

type\="range"

min\="0"

max\="360"

value\={hue}

onChange\={(e) \=> setHue(Number.parseInt(e.target.value))}

className\="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"

style\={{

background: \`linear-gradient(to right,

hsl(0, ${saturation}%, ${lightness}%),

hsl(60, ${saturation}%, ${lightness}%),

hsl(120, ${saturation}%, ${lightness}%),

hsl(180, ${saturation}%, ${lightness}%),

hsl(240, ${saturation}%, ${lightness}%),

hsl(300, ${saturation}%, ${lightness}%),

hsl(360, ${saturation}%, ${lightness}%))\`,

}}

/>

</label\>

<label className\="block text-sm text-zinc-950/70 dark:text-white/70"\>

Saturation: {saturation}%

<input

type\="range"

min\="0"

max\="100"

value\={saturation}

onChange\={(e) \=> setSaturation(Number.parseInt(e.target.value))}

className\="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"

style\={{

background: \`linear-gradient(to right,

hsl(${hue}, 0%, ${lightness}%),

hsl(${hue}, 50%, ${lightness}%),

hsl(${hue}, 100%, ${lightness}%))\`,

}}

/>

</label\>

<label className\="block text-sm text-zinc-950/70 dark:text-white/70"\>

Lightness: {lightness}%

<input

type\="range"

min\="0"

max\="100"

value\={lightness}

onChange\={(e) \=> setLightness(Number.parseInt(e.target.value))}

className\="w-full h-2 bg-zinc-950/20 rounded-lg appearance-none cursor-pointer dark:bg-white/20 mt-1"

style\={{

background: \`linear-gradient(to right,

hsl(${hue}, ${saturation}%, 0%),

hsl(${hue}, ${saturation}%, 50%),

hsl(${hue}, ${saturation}%, 100%))\`,

}}

/>

</label\>

</div\>

<div className\="flex space-x-2"\>

{colors.map((color, idx) \=> (

<div

key\={idx}

className\="h-16 rounded flex-1 cursor-pointer transition-transform hover:scale-105"

style\={{ backgroundColor: color }}

title\={\`Click to copy: ${color}\`}

onClick\={() \=> copyToClipboard(color)}

/>

))}

</div\>

<div className\="text-sm font-mono text-zinc-950/70 dark:text-white/70"\>

<p\>

Base color: hsl({hue}, {saturation}%, {lightness}%)

</p\>

</div\>

</div\>

</div\>

)

}