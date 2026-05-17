# Draft Corrections: Post 13 - The Machine That Learned Too Early (Perceptron)

Date: 2026-05-17
Post: `/_posts/2026-04-09-The-machine-that-learned-too-early.md`

Summary: Post is very accurate overall. Three minor edits recommended, plus one citation that should be tightened.

## Correction 1: Telescope size (12 → 12.5 inch)

### Location
Line 26, paragraph 1 of "Frank Rosenblatt" section.

### Current text
> He built a personal observatory on a hilltop behind his house, doing most of the masonry himself, and housed a **12-inch Cassegrain telescope** inside it.

### Proposed text
> He built a personal observatory on a hilltop behind his house, doing most of the masonry himself, and housed a **12.5-inch Cassegrain telescope** inside it.

### Source
UMass Computational Phonology memorial: "Fecker 12-1/2" Cassegrain, complete with equatorial mount and drive."

---

## Correction 2: "20 training examples" claim for X-vs-E

### Location
Line 68, "Hardware Machine" subsection.

### Current text
> The Mark I Perceptron achieved 99.8% accuracy distinguishing squares from circles, 100% on squares versus diamonds, and **could classify the letters X and E with 100% accuracy after just 20 training examples**.

### Issue
Wikipedia's Mark I Perceptron article corroborates the 99.8% on shapes, 100% on squares-vs-diamonds, and 100% on X-vs-E (with limited rotation). It does NOT mention "20 training examples" specifically. The figure may come from the Mark I Operators' Manual but is not corroborated by the standard sources I consulted.

### Proposed text (Option A -- remove the unverified detail)
> The Mark I Perceptron achieved 99.8% accuracy distinguishing squares from circles, 100% on squares versus diamonds, and 100% accuracy classifying the letters X and E (with limited rotation).

### Proposed text (Option B -- keep but cite the manual)
Add footnote citing Hay, J., Lynch, B. & Smith, D. (1960). *Mark I Perceptron Operators' Manual*. Cornell Aeronautical Laboratory Report VG-1196-G-1 (DTIC AD0236965), if that document supports the figure.

### Recommendation
Option A unless the user can confirm the 20-examples figure from the operators' manual or Rosenblatt's reports.

---

## Correction 3: Tighten footnote [^3] citation for the hidden-layer prediction

### Location
Lines 110, 193 (footnote [^3]).

### Current text (in body)
> Minsky and Papert wrote that adding hidden layers might help, but then added: "Virtually nothing is known about the computational capabilities of this latter kind of machine. We believe that it can do little more than can a low order perceptron."[^3]

### Current footnote
> [^3]: Minsky, M. & Papert, S. (1969). *Perceptrons: An Introduction to Computational Geometry*. MIT Press, p. 232.

### Issue
The quote IS authentic Minsky-Papert; however, Wikipedia's *Perceptrons (book)* article attributes the wording to the "1971 Report of Project MAC" (Minsky and Papert), with that passage paraphrased into the 1988 expanded edition's prologue. The page-232 citation to the 1969 first edition has not been independently verified. The quote may indeed appear on or near p. 232 of the 1969 edition, but the safer attribution is the 1988 prologue.

### Recommendation
Either: (a) verify p. 232 from a physical/scan copy of the 1969 first edition and keep the citation; or (b) reword the footnote to:
> [^3]: Minsky, M. & Papert, S. (1988). *Perceptrons: An Introduction to Computational Geometry*. Expanded edition, MIT Press. Prologue. (The passage originates from Minsky & Papert's 1971 Report of Project MAC.)

---

## Verified-correct items NOT requiring correction

Despite triple-checks, the following details are accurate and do not need editing:
- Rosenblatt born July 11, 1928, New Rochelle, NY.
- Died July 11, 1971 (43rd birthday) drowning in Chesapeake Bay.
- Bronx Science 1946; Cornell A.B. 1950, Ph.D. 1956.
- Cornell Aeronautical Laboratory in Buffalo.
- Project PARA, Report 85-460-1, January 1957.
- Mark I: 400 photocells (20x20), 512 association units, 8 response units, potentiometers, electric motors, ONR funding, Smithsonian.
- New York Times July 8, 1958, page 25, "walk, talk, see, write, reproduce itself and be conscious of its existence."
- Rosenblatt quote: "the first machine which is capable of having an original idea."
- Minsky SNARC 1951 at Princeton, ~40 Hebb synapses, vacuum tubes, with Dean Edmonds.
- 1956 Dartmouth Conference as founding event.
- Minsky-Papert *Perceptrons* 1969 MIT Press, XOR problem, linear separability.
- Necronomicon comparison.
- McCulloch-Pitts 1943 paper, neurophysiologist + logician.
- Lighthill 1973 report quote and "all but two universities" funding cuts.
- Mansfield Amendment 1969.
- ALPAC 1966.
- Hopfield 1982 (physicist, PNAS).
- Rumelhart, Hinton, Williams 1986 *Nature* "Learning representations by back-propagating errors."
- Werbos 1974, Linnainmaa 1970.
- AlexNet 2012, 8 layers, 15.3% top-5 error, runner-up 26.2% (which rounds correctly from 26.172%), two Nvidia GPUs.
- Krizhevsky's bedroom training claim is widely repeated; consistent with sources.
- "60 years too soon" is from Cornell Chronicle 2019 headline (already cited).

## Overall assessment
This is a high-quality post with very few factual errors. The three suggested edits are minor: a telescope-size off-by-half-inch, an unverified training-set-size figure, and a citation that could be tightened. The post's central thesis -- Rosenblatt invented learning machines, Minsky and Papert overshadowed neural networks for a generation, deep learning vindicated the perceptron approach in 2012 -- is well-supported throughout.
