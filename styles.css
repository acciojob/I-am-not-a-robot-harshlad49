const imageClasses = ['img1', 'img2', 'img3', 'img4', 'img5'];
const container = document.getElementById('image-container');
const resetBtn = document.getElementById('reset');
const verifyBtn = document.getElementById('verify');
const message = document.getElementById('h');
const result = document.getElementById('para');

let selectedImages = [];
let selectedIndexes = [];

function getRandomDuplicate(images) {
  const duplicateIndex = Math.floor(Math.random() * images.length);
  return images[duplicateIndex];
}

function shuffle(array) {
  return array.sort(() => 0.5 - Math.random());
}

function renderImages() {
  container.innerHTML = '';
  selectedImages = [];
  selectedIndexes = [];
  result.textContent = '';
  resetBtn.style.display = 'none';
  verifyBtn.style.display = 'none';
  message.textContent = 'Please click on the identical tiles to verify that you are not a robot.';

  // Clone and insert duplicate
  let imagesWithDuplicate = [...imageClasses];
  const duplicate = getRandomDuplicate(imagesWithDuplicate);
  imagesWithDuplicate.push(duplicate);

  const shuffled = shuffle(imagesWithDuplicate);

  shuffled.forEach((cls, index) => {
    const img = document.createElement('img');
    img.classList.add(cls);
    img.dataset.imgClass = cls;
    img.addEventListener('click', () => handleClick(img, index));
    container.appendChild(img);
  });
}

function handleClick(img, index) {
  if (selectedIndexes.includes(index) || selectedImages.length >= 2) return;

  img.classList.add('selected');
  selectedImages.push(img.dataset.imgClass);
  selectedIndexes.push(index);

  if (selectedImages.length > 0) resetBtn.style.display = 'inline-block';
  if (selectedImages.length === 2) verifyBtn.style.display = 'inline-block';
}

resetBtn.addEventListener('click', () => {
  renderImages();
});

verifyBtn.addEventListener('click', () => {
  verifyBtn.style.display = 'none';
  if (selectedImages[0] === selectedImages[1]) {
    result.textContent = 'You are a human. Congratulations!';
  } else {
    result.textContent = "We can't verify you as a human. You selected the non-identical tiles.";
  }
});

renderImages();
