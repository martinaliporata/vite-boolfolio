<script>
export default {
    data() {
        return {

        }
    },
    props: {
        image: {
            type: String,
            required: false
        },
        title: {
            type: String,
            required: true
        },
        author: {
            type: String,
            required: true
        },
        date: {
            type: String,
            required: true
        },
        preview: {
            type: String,
            required: true
        },
        type: {
            type: String,
            required: true
        }
    }
}
</script>

<template>
    <div class="project-card">
        <img :src="image" alt="project image" class="project-image" />
        <div class="project-content">
            <h2 class="project-title">{{ title }}</h2>
            <p class="project-author">{{ author }}</p>
            <p class="project-date">{{ date }}</p>
            <p class="project-preview">{{ preview }}</p>
            <span class="project-type">{{ type }}</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>

@use "../style/partials/_variables" as *;
.projects-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 20px;
  padding: 20px;
}

// Card styles
.project-card {
  background-color: $card-bg-color;
  border-radius: $card-border-radius;
  box-shadow: $card-shadow;
  overflow: hidden;
  width: $card-width;
  display: flex;
  flex-direction: column;
  transition: transform 0.3s, box-shadow 0.3s;

  &:hover {
    transform: translateY(-5px);
    box-shadow: $card-hover-shadow;
  }
}

// Image styles
.project-image {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

// Content styles
.project-content {
  padding: 15px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

// Title styles
.project-title {
  font-size: $font-size-title;
  font-weight: bold;
  color: $color-primary;
}

// Author styles
.project-author {
  font-size: $font-size-author;
  color: $color-secondary;
}

// Date styles
.project-date {
  font-size: $font-size-date;
  color: $color-tertiary;
}

// Preview styles
.project-preview {
  font-size: $font-size-preview;
  color: $color-primary;
  margin-top: 10px;
}

// Type ID styles
.project-type {
  align-self: flex-end;
  background-color: $color-type-bg;
  color: $color-type-text;
  padding: 5px 10px;
  border-radius: 4px;
  font-size: $font-size-type;
}
</style>