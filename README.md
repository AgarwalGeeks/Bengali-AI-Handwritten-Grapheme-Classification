<h2>Abstract</h2>
<p>
  Bengali is the 5th most spoken language in the world with hundreds of million of speakers. It’s the official language of Bangladesh and the second most spoken language in India. Considering its reach, there’s significant business and educational interest in developing AI that can optically recognize images of the language handwritten. This challenge hopes to improve on approaches to Bengali recognition.



Optical character recognition is particularly challenging for Bengali. While Bengali has 49 letters (to be more specific 11 vowels and 38 consonants) in its alphabet, there are also 18 potential diacritics, or accents. This means that there are many more graphemes, or the smallest units in a written language. The added complexity results in ~13,000 different grapheme variations (compared to English’s 250 graphemic units).

Bangladesh-based non-profit Bengali.AI is focused on helping to solve this problem. They build and release crowdsourced, metadata-rich datasets and open source them through research competitions. Through this work, Bengali.AI hopes to democratize and accelerate research in Bengali language technologies and to promote machine learning education.

For this competition, you’re given the image of a handwritten Bengali grapheme and are challenged to separately classify three constituent elements in the image: grapheme root, vowel diacritics, and consonant diacritics.

By participating in the competition, you’ll hopefully accelerate Bengali handwritten optical character recognition research and help enable the digitalization of educational resources. Moreover, the methods introduced in the competition will also empower cousin languages in the Indian subcontinent.
</p>
<br>
<h2>Dataset</h2>
<p>This dataset contains images of individual hand-written Bengali characters. Bengali characters (graphemes) are written by combining three components: a grapheme_root, vowel_diacritic, and consonant_diacritic. Your challenge is to classify the components of the grapheme in each image. There are roughly 10,000 possible graphemes, of which roughly 1,000 are represented in the training set. The test set includes some graphemes that do not exist in train but has no new grapheme components. It takes a lot of volunteers filling out sheets like this to generate a useful amount of real data; focusing the problem on the grapheme components rather than on recognizing whole graphemes should make it possible to assemble a Bengali OCR system without handwriting samples for all 10,000 graphemes.</p>
<br>
<p>Files
train.csv<br>
image_id: the foreign key for the parquet files<br>
grapheme_root: the first of the three target classes<br>
vowel_diacritic: the second target class<br>
consonant_diacritic: the third target class<br>
grapheme: the complete character. Provided for informational purposes only, you should not need to use this.<br>
test.csv<br>
Every image in the test set will require three rows of predictions, one for each component. This csv specifies the exact order for you to provide your labels. -<br> row_id: foreign key to the sample submission -<br> image_id: foreign key to the parquet file - component: the required target class for the row (grapheme_root, vowel_diacritic, or consonant_diacritic)

sample_submission.csv<br>
row_id: foreign key to test.csv<br>
target: the target column</p><br>
<h2>Setup</h2>
<p>
  pip install cv2<br>
  pip install keras<br>
  pip install matplotlib<br>
  pip install numpy <br>
  pip install pandas<br>
  pip install seaborn<br>
</p>
<h2>Model: Convolutional Network</h2>
<h2>Accuracy: 98%</h2>
