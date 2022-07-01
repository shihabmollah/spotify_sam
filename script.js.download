console.log("Welocome to MOOD");
//Initialize the variables
let songindex=0;
let audioElement = new Audio('songs\1.mp3');
let masterPlay=document.getElementById('masterPlay');
let myprogessBar=document.getElementById('myprogressBar');
let gif=document.getElementById('gif');
let masterSongName=document.getElementById('masterSongName');
let songItem=Array.from(document.getElementsByClassName('songItem'));


let songs=[
    {songsName: "pani pani",filepath: "songs\1.mp3", coverpath:"cover.jpeg"},
    {songsName: "DE TALI",filepath:"songs\2.mp3", coverpath:"cover2.jpeg"},
    {songsName: "SHAPE-OF YOU",filepath:"songs\3.mp3", coverpath:"cover3.jpeg"},
    {songsName: "LET-ME-LOVE-U",filepath:"songs\4.mp3", coverpath:"cover4.jpeg"},
    {songsName: "HALKI-HALKI-SI-BARSHAT",filepath:"songs\5.mp3", coverpath:"cover5 (1).jpeg"},
    {songsName: "RANG-SARI",filepath:"songs\6.mp3", coverpath:"cover5 (2).jpeg"},
    {songsName: "MAKHNA",filepath:"songs\7.mp3", coverpath:"cover5 (3).jpeg"},
    {songsName: "DANCE-MERI-RANI",filepath:"songs\8.mp3", coverpath:"cover5 (4).jpeg"},
   
]
songItem.forEach((element,i)=>{
    element.getElementsByTagName("img")[0].src=songs[i].coverpath;
    element.getElementsByClassName("songsName")[0].innerText=songs[i].songsName;

})
//audio element play ();
//handle play pause click
masterPlay.addEventListener('click', ()=>{
    if(audioElement.paused || audioElement.currentTime<=0){
        audioElement.play();
        masterPlay.classList.remove('fa-circle-play');
        masterPlay.classList.add('fa-circle-pause');
        gif.style.opacity=1;
    }
    else{
        audioElement.pause();
        masterPlay.classList.remove('fa-circle-pause');
        masterPlay.classList.add('fa-circle-play');
        gif.style.opacity=0;
    }
})


//Listen to Events
audioElement.addEventListener('timeupdate',()=>{
    console.log('timeupdate');
    //Update seek bar
   progress=parseInt((audioElement.currentTime/audioElement.duration)*100);
    console.log(progress);
    myprogessBar.value=progress;
})
myprogessBar.addEventListener('change',()=>{
audioElement.currentTime=myprogessBar.value*audioElement.duration/100;
})

const makeAllPlays = ()=>{
    Array.from(document.getElementsByClassName('songItemPlay')).forEach((element)=>{
    element.classList.remove('fa-circle-pause');
    element.classList.add('fa-circle-play');
    

    })
}
Array.from(document.getElementsByClassName('songItemPlay')).forEach((element)=>{
    element.addEventListener('click',(e)=>{
        console.log(e.target);
        makeAllPlays();
        songindex=parseInt(e.target.id);
        e.target.classList.remove('fa-circle-play');
        e.target.classList.add('fa-circle-pause');
        audioElement.src=`songs/${songindex+1}.mp3`;
        masterSongName.innerText=songs[songindex].songsName;
        audioElement.currentTime=0;
        audioElement.play();
        gif.style.opacity=1;
        masterPlay.classList.remove('fa-circle-play');
        masterPlay.classList.add('fa-circle-pause');
    })

})
document.getElementById('next').addEventListener('click',()=>{
    if(songindex>=7){
        songindex=0;
    }
    else{
    songindex+=1;
    }
    audioElement.src=`songs/${songindex+1}.mp3`;
    masterSongName.innerText=songs[songindex].songsName;
    audioElement.currentTime=0;
    audioElement.play();
    masterPlay.classList.remove('fa-circle-play');
    masterPlay.classList.add('fa-circle-pause');
})
document.getElementById('previous').addEventListener('click',()=>{
    if(songindex<=0){
        songindex=0;
    }
    else{
    songindex-=1;
    }
    audioElement.src=`songs/${songindex+1}.mp3`;
    masterSongName.innerText=songs[songindex].songsName;
    audioElement.currentTime=0;
    audioElement.play();
    masterPlay.classList.remove('fa-circle-play');
    masterPlay.classList.add('fa-circle-pause');
})