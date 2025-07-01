fetch('videos.json')
.then(response => response.json())
.then(data => {
const container = document.getElementById('video-list');
data.forEach(video => {
const div = document.createElement('div');
div.className = 'video-item';
div.innerHTML = `
<iframe src="https://www.youtube.com/embed/${video.youtubeId}" frameborder="0" allowfullscreen></iframe>
<p>${video.title}</p>
`;
container.appendChild(div);
});
})
.catch(error => console.error('Errore caricamento video:', error));