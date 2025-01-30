<template>
  <div class="showreel-bio-container">
    <!-- Video Section -->
    <div class="video-section">
      <video controls autoplay class="showreel-video" loading="lazy">
        <source src="~/assets/videos/thevideo.mp4" type="video/mp4" />
        Your browser does not support the video tag.
      </video>
    </div>

    <!-- Bio Section -->
    <div class="bio-section">
      <p class="bio-text">
        Tess Salinger is a Digital Designer based in Melbourne/Naarm,
        driven by a passion for visual storytelling. She is fascinated by
        uncovering the beauty in everyday moments and translating
        them into captivating narratives. With expertise in After Effects,
        DaVinci, Nuke and Premiere Pro for video editing, Maya for 3D design,
        Illustrator for graphic design, and Unity for interactive experiences,
        Tess navigates these platforms to bring her creative visions to life.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ShowreelBio',
};
</script>

<style scoped>
.showreel-bio-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 40px;
  padding: 40px;
  max-width: 1200px;
  margin: 0 auto;
}

.video-section {
  flex: 1;
  max-width: 50%;
}

.showreel-video {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.bio-section {
  flex: 1;
  max-width: 50%;
}

.bio-text {
  font-size: 1.5rem;
}

@media only screen and (max-width: 768px) {
  .showreel-bio-container {
    flex-direction: column;
    /* Stack video and bio vertically */
    gap: 20px;
    /* Reduce gap for smaller screens */
  }

  .video-section,
  .bio-section {
    max-width: 100%;
    /* Full width on smaller screens */
  }
}
</style>
