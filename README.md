# creative-commons-autocopyright-hugo
A partial for hugo, intended to automatically let you apply creative commons licenses to pages via the use of a "permission" page parameter.

It works by generating the image and deed links piecemeal via Hugo's .Page.Store.Add function, which allows for things like having the badge show EU currency, changing which badge is being shown, and (potentially) showing non-png files. It then uses the image link to get the badges off [this page](https://creativecommons.org/mission/downloads/), and the deed link (which is just called "link") to reference the applicable CC license terms.

This code expects the caller to filter out non-creative-commons permission types: failing to do so could result in bugs. Additional bugs could be caused by the official creative commons website going down or changing its favored set of licenses.

For this function, inputs are expected to be capitalized, begin with BY, exclude the version number, and have dashes between the letter pairs (E.G, "BY-SA", "BY-ND-NC"). However, I have tried to account for letter pairs getting flipped.

This is an example of the partial in use on my website:
<img width="867" height="377" alt="Screenshot from 2026-05-23 11-07-01" src="https://github.com/user-attachments/assets/aa85fd4d-a3df-4585-8ced-b3030c83132b" />
