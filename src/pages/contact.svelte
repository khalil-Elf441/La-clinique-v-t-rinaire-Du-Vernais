<h1>Contact</h1>

<script>
    import ReadMore from "svelte-read-more";
    
    // declaring a content variable

  

        import CollapsibleCard from 'svelte-collapsible-card'
        
        const items = [
            {
                title: 'Leash Training for Better Fitness',
                img: 'https://img.webmd.com/dtmcms/live/webmd/consumer_assets/site_images/article_thumbnails/features/_2017/01_2017/leash_training_dog_features/1800x1200_leash_training_dog_features.jpg?resize=300px:*',
                text: 'oure in the mall The plan is to go to just one store But you hear a voice that says Go ahead Walk over there Look at that shiny thing in the window Oh and that one too And whats that over there This is your dog on a walk Their nature is to smell and explore everything around them Want to know whats unnatural to them Walking on a leash But your dog needs to walk and you need to use a leash to control them The exercise is good for both of you And a wellwalked pooch is a happy and healthy one Taking a dog on a walk helps them explore their environment which is key to their wellbeing says James Barr DVM with Texas AMs Veterinary School A walk shouldnt only be a chance for your pet to go to the bathroom A good stroll is like a spa for them Daily walks can also aid your dogs digestion and help them sleep better at night On the other hand idle paws can lead to bad habits Chewing digging and tons of barking often mean one thing  boredom Walking helps hounds burn off the jitters It also gives the two of you time to bond  and build trust'


            },
            {
                title: 'Tips to Get Out With Your Older Dog',
                img: 'https://img.webmd.com/dtmcms/live/webmd/consumer_assets/site_images/article_thumbnails/other/walking_with_dog_other/1800x1200_walking_with_dog_other.jpg?resize=300px:*',
                text: 'Step One Find the Right Time Brush your dogs teeth when they are calm and relaxed Your goal Set a routine Working up to brushing daily is ideal But if their mouth is healthy even three days a week can make a difference Without brushing plaque can build up putting your dog at risk for bad breath gum disease and tooth decay It can also cause painful infections Severe infection can spread causing lifethreatening conditions.Step Two Gather Your Tools Youll want to use a toothbrush made for dogs The bristles are softer and specially angled Finger brushes can work well for dogs under 30 pounds For larger dogs longer handles can give you better reach Be sure to use dog toothpaste too It comes in dogfriendly flavors like poultry or peanut butter Never use human toothpaste it contains ingredients that may hurt your dogs stomach'
            },
            {
                title: 'Why Dogs Bark and Curbing Excessive Barking',
                subtitle: 'I am the third card',
                img: 'https://img.webmd.com/dtmcms/live/webmd/consumer_assets/site_images/article_thumbnails/other/dog_running_other/1800x1200_dog_running_other.jpg?resize=300px:*',
                text: 'No one should expect a dog to never bark Thats as unreasonable as expecting a child to never talk But some dogs bark excessively If thats a problem in your home the first step is figuring out what causes your dog to bark too much Once you know why they are barking you can start to treat their barking problemWhy Dogs Bark Barking is one type of vocal communication that dogs use and it can mean different things depending on the situation Here are some reasons why dogs bark TerritorialProtective When a person or an animal comes into an area your dog considers their territory that often triggers excessive barking As the threat gets closer the barking often gets louder Your dog will look alert and even aggressive during this type of barkingAlarmFear Some dogs bark at any noise or object that catches their attention or startles them This can happen anywhere not just in their home territory Their ears will be back and tail tucked when they are in a state of fear BoredomLoneliness Dogs are pack animals Dogs left alone for long periods whether in the house or in the yard can become bored or sad and often will bark because they are unhappy'
            }
        ]
    
    </script>
    
    <ul>
        
        { #each items as item }
            <li>
                <CollapsibleCard>
                    
                    <div slot='header' class='header'>
                        <img src={item.img} alt=""/>
                        <div class='titles'>
                            <h2>{ item.title }</h2>
                            <ReadMore textContent={item.text} maxChars={10}/>
                        </div>
                    </div>
                    
                
                </CollapsibleCard>
            </li>
        { /each }
    
    </ul>
    
    <style>
    
        ul {
            list-style: none;
            padding: 0;
            margin: 0 auto;
            width: 90%;
            max-width: 900px;
            color: rgb(50,50,50);
            font-size: 1.1rem;
        }
        
        li {
            margin-bottom: 0em;
            border-bottom: 1px solid rgb(200,200,200);
        }
        
        .header {
            padding: 0.5em;
            display: flex;
        }
        
        img {
            display: block;
            border-radius: 5px;
        }
        
        .titles {
            padding: 0 0 0 1em;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        
        h2 {
            margin: 0;
            width: 100%;
        }
        
        p {
            margin: 0;
        }
        
        .body {
            padding: 0.5em;
        }
    </style>
    