<template>
    <div class="card-character">
        <img :src="character.image" alt="character.image">
        <div class="card-character__info">
            <h3>{{ character.name }}</h3>
            <div class="status">
                <span 
                    :class=" 
                        character.status == 'Alive' ? 'alive' :
                        character.status == 'Dead' ? 'dead' :
                        'default' 
                    "
                ></span>
                <!-- <span>{{ character.gender }}</span><br> -->
                <span>{{ character.status }} - {{ character.species }}</span>
            </div>
            <div class="origin">
                <span>
                    Origin:
                    {{ character.origin.name }}
                </span>
            </div>
            <div class="location">
                <span>
                    Location:
                    {{ character.location.name }}
                </span>
            </div>
        </div>
    </div>  
</template>

<script>
export default {
    props: ['character']
}
</script>

<style lang="scss">
.card-character {
    height: 100%;
    background-color: var(--background-card) ;
    border-radius: 20px;
    box-shadow: 0 0 10px 1px var(--background-body);
    overflow: hidden;
    cursor: pointer;
    transition: transform 200ms ease-in-out;
    &:hover {
        transform: scale(1.05);
        h3 {
            color: var(--text-orange);
        }
    }

    span {
        color: var(--text-gray);
    }

    h3 {
        margin-bottom: 0.5rem;
    }
    
    &__image {
        height: 100%;
        width: 100%;
        background-color: var(--background-card);
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
    }

    &__info {
        padding: 1.5rem;
        .status {
            display: flex;
            align-items: center;
            margin-bottom: 0.5rem;
            span {
                color: var(--text-gray);
                &:first-child{
                    width: 10px;
                    height: 10px;
                    border-radius: 50%;
                    margin-right: 0.5rem;
                }
            }
            .alive {
                background-color: green;
            }
            .dead {
                background-color: red;
            }
            .default {
                background-color: white;
            }
        }
        .origin {
            margin-bottom: 0.5rem;
        }
    }
}

</style>