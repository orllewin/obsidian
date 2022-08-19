<iframe
	border=0
	frameborder=0
	height=450
	width=450 
	src="https://orllewin.github.io/coracle/embed/bezier.html">
</iframe>

A [Bézier Curve](https://en.wikipedia.org/wiki/B%C3%A9zier_curve)

## Syntax

`val bezier = Bezier(anchor1, control1, control2, anchor2)`
`val bezier = Bezier(anchor1, control1, control2, anchor2, detail)`
`val bezier = Bezier(x1, y1, x2, y2, x3, y3, x4, y4)`
`val bezier = Bezier(x1, y1, x2, y2, x3, y3, x4, y4, detail)`
  
Bezier has a builtin `draw()` method: `bezier.draw()`

The raw lines are also available if you want more control:

```kotlin

val colourA = Color.random()
val colourB = Color.random()
bezier.lines.forEachIndexed { index, line ->
    stroke(Color.lerp(colourA, colourB, (index.toFloat()/bezier.lines.size)))
    line(line)
}
```

## Example Source
```kotlin
import coracle.Drawing
import coracle.random
import coracle.shapes.Bezier
import coracle.shapes.Line
import coracle.shapes.Point

class ReferenceBezier: Drawing() {

    private val w = 450
    private val h = 450
    private val agent1A = Agent()
    private val agent1B = Agent()
    private val agent2A = Agent()
    private val agent2B = Agent()

    val line1 = Line()
    val line2 = Line()

    override fun setup() {
        size(w, h)
    }

    override fun draw() {
        background(0xf5f2f0)

        line1.update(agent1A, agent1B)
        line2.update(agent2A, agent2B)

        stroke(0x88cc99)
        line1.draw()
        line2.draw()

        agent1A.move()
        agent1B.move()
        agent2A.move()
        agent2B.move()

        val bezier = Bezier(agent1A, agent1B, agent2A, agent2B, 25)
        stroke(0xcc9988)
        bezier.draw()
    }

    inner class Agent: Point() {

        private var xDirection = 1
        private var yDirection = 1

        init {
            x = random(w)
            y = random(h)

            xDirection = when {
                random(100) > 50 -> 1
                else -> -1
            }

            yDirection = when {
                random(100) > 50 -> 1
                else -> -1
            }
        }

        fun move(){
            when {
                x > width || x < 0 -> xDirection *= -1
            }
            when {
                y > height || y < 0 -> yDirection *= -1
            }

            x += (2 * xDirection)
            y += (2 * yDirection)
        }
    }
}
```