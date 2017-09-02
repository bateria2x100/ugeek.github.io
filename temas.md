---
layout: page
title: Temas
desc: "Lista de post ordenados por etiquetas"
permalink: /Temas/

sitemap:
  priority: .5

---

---
<!-- Begin SpeakPipe code -->
<script type="text/javascript">
(function(d){
var app = d.createElement('script'); app.type = 'text/javascript'; app.async = true;
var pt = ('https:' == document.location.protocol ? 'https://' : 'http://');
app.src = pt + 'www.speakpipe.com/loader/u33wn17v7gblat29taobg3x8q901jwfj.js';
var s = d.getElementsByTagName('script')[0]; s.parentNode.insertBefore(app, s);
})(document);
</script>
<!-- End SpeakPipe code -->




**Terminal**  
1. [Antergos. Comandos para terminal y derivadas de Arch Linux](/Antergos-comando-para-terminal-y-derivadas-arch/)  
2. [Crear un USB con una ISO de una distro](https://ugeek.github.io/Crear-un-usb-con-iso/)  
3. [Alias en Bash. (.bashrc)](https://ugeek.github.io/Alias-en-bash/)  



---  


**Servicios**  
1. [Docker en Ubuntu, Antergos y derivadas en menos de 10 minutos](https://ugeek.github.io/Docker-en-Ubuntu-Antergos-en-menos-de-10-minutos/)  

---  

**GitHub**  
1. [Configurar GitHub en tu Pc mediante la terminal](/GitHub.-Configurarlo-en-tu-Pc-mediante-la-terminal/)  
2. [Comandos GitHub en la Terminal.](/GitHub-en-la-Terminal.-Comandos/)  
3. [Crear un Blog Jekyll desde la Terminal](/Crear-un-blog-jekyll-desde-la-terminal/)  

---

**Jekyll**  
1. [Instalar Ruby y Jekyll](/Instalar-Ruby-y-Jekyll/)  
2. [Crear el Feed para el podcast](/generar-feed-para-podcast-en-jekyll/)  


---  

**Aplicaciones**  
1. [Synapse](/Synapse/)  

---

*Podcast*   


Abre con VLC
<a href="https://ugeek.github.io/ugeek.m3u"><img style="float: left;" src="/img/icon/play.png" alt="" width="30" height="30" /></a>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>HTML5 Audio Player</title>
    <script type="text/javascript" src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

    <script type="text/javascript" >
    var audio;
    var playlist;
    var tracks;
    var current;
    var previous;
    var current_track;
    var previous_track;
    var ntracks;
    function initaudio(){
        audio=$("audio");
        playlist=$("#playlist");
        ntracks=$("[id^=item-]").length
        audio[0].volume=1;
        current=0;
        previous=ntracks-1;
        current_track=playlist.find("#item-0");
        previous_track=playlist.find("#item-"+previous);
        runaudio(current_track, audio[0],false);
        $("[id^=item-]").click(function(e){
            e.preventDefault();
            previous=current;
            previous_track=current_track;
            remove_play(previous_track);
            current_track=$(this);
            current=current_track.parent().index();
            runaudio(current_track, audio[0]);
        });
        audio[0].addEventListener("ended",function(e){
            playnext();
        });
        audio[0].addEventListener("pause",function(e){
            $("#playing").hide();
        });
        audio[0].addEventListener("play",function(e){
            $("#playing").show();
        });
    };
    function playnext(){
        previous=current;
        previous_track=current_track;
        remove_play(previous_track);
        current++;
        current_track=playlist.find("#item-"+current);
        if(current_track.length==0){
            current=0;
            current_track=playlist.find("#item-0");
        }
        runaudio($(current_track),audio[0]);
    }
    function playprevious(){
        previous=current;
        previous_track=current_track;
        remove_play(previous_track);
        current--;
        current_track=playlist.find("#item-"+current);
        if(current<0){
            current=ntracks-1;
        }
        current_track=playlist.find("#item-"+current);
        runaudio($(current_track),audio[0]);
    }
    function remove_play(item){
        isp=$(item.find(".isplaying"));
        isp.html("");
    }
    function runaudio(item, player,play=true){
        isp=$(item.find(".isplaying"))
        isp.html("<i class='fa fa-play' aria-hidden='true'></i>");
        podcast=$(item.find(".podcast"));
        $("#podcast").text(podcast.text());
        track=$(item.find(".track"));
        if(track.text().length>33){
            $("#track").text(track.text().substring(0,30)+"...");
        }else{
            $("#track").text(track.text());
        }
        link=$(item.find('a'));
        player.src=link.attr("href");
        par=link.parent();
        par.addClass("active").siblings().removeClass("active");
        audio[0].load();
        if(play==true){
            console.log(play);
            audio[0].play();
        }
    }
    $(document).ready(function(){
        console.log($("[id^=item-]").length);
        $("#right").bind("click", function(e) {
            playnext();
        });
        $("#left").bind("click", function(e) {
            playprevious();
        });
        $("#playing").hide();
        initaudio();
    });
    </script>
    <link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
    <style>
        #left{
            margin-top: 7px;
            float: left;
            width: 16px;
            height: 32px;
            cursor:hand;
        }
        #right{
            margin-top: 7px;
            float:left;
            width: 16px;
            height: 32px;
            cursor:hand;
        }
        .compilandopodcast{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEUREyMZGywnGS1HGi1BIEEsLz9/HjfqHTe7LkQ0VktMTloAcBB9R1b6KUJHWXo1ckbFUV5pbHT4R1v2WGoAsw/Mb3robXyFipGghpqorbD2nqb2ur3Mz9Dz19jn6OX4+fWMNKc4AAAAAWJLR0QAiAUdSAAAAAlwSFlzAAAN1wAADdcBQiibeAAAAAd0SU1FB+EFBQoqJLANsOoAAAJcSURBVEjHzZQBd6MgDIBRCzKsrIBCISD//18uUNe6XbW3d+/dXVoxJHwkAYE0PxTyNwGqPm2ECpTnk20Bv77dkqtEcQAIHHfz+3V4RRTZAahoXC4ALcMXJygVviCePAWILwzqAsd7QVBTShFVeoerVOZ3N1Upx89N/CUG2VZMMIvPrIVSQjgaH5ZvAE5M1CaDYZr8uY0UK6LPAF8qwIRQdb5UL05SymEYBIbYqwErxvD0lrbygimPbfxaxVbHjDA6pl3qFs5RJSV1WNce4HIs6dKas2CMKeeQq9M8BXyOD3iYBvdGhZQYV7wGYm6u3RrjEKD3+odJOu/VdXg/Au5LTijOT+UV984fARuX9PFtmiTn8RCI9750lJ2u0pXP8QB4+IY354fpXX4xPgHuVZQv43RSLr8A8rJaMP/ovcwvgbzU89PIU4dZ5UPARZR6+BFhJ1qHo2nZA0gRVe+A6CuKO1lsxxcZdfdLYxG/dfMRPAtFnCD/+m79IdC2bWlv77XTbl0bgF1mzvh8YRfOL/xSlQtrOtT4auItn2e+Au2cbNKLAbMAJJN00tlm3ZwXgw6w2Sw29MmGwFYgwNjr3INdgk3oXXQ2Bcg2BfzhHD2YbCx8AjMY0FmDTVaXCLpHwBiz9BCSMWiyYYRHhIZpM3JtdK/xNWreMWyNGXVv9M1kRsaNHrs/3Ye269oGn64ratHa2mv3gC6BMQA6AZ8hjAGshaAB+D5gbdAW1xigH3XC4Sb0wbB9YBwtlO0wNmAgjAa4orbbBThuL6/Cyp9VjfHdGpp2fR7975b/8jx8AEVRQRkFDsQrAAAAAElFTkSuQmCC");
        }

        .eduardocollado{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEUAAwAHAQIICwYOEA0aHBknKCU0NjE+QjxGSkROUk1TVkhUWVNdYVtkaWNqcWFvdG5+hXyDhYGRk46OlYycoJqmqqSusqy3urXAw7/LzsvY2tfj5eLs7uvx8/D3+fb9//wadFjiAAAAAWJLR0QAiAUdSAAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB+EFBQoqBItjkCIAAABBdEVYdENvbW1lbnQAQ1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gOTAKsEVYkwAABBVJREFUSMeVlut2tCoMhikKSIEiSDiKc/93uYNjO/awf3yZrjWti8ckbw6U9D0lLSbyhkbI+fVGZmVXCKW0/svI48h5NfQ6SS6MrauFENvjlw0gbIzQCX8oneZpmueJMruFNQKU4w8geUEJJdwapVwI4JyR7H210fsA+fgFdMCACOEhl1L3vR8PzMq9C66s5Nz+JEgvfsbzk8q1DUPk0VMBxdmMAc6m/AAaKDxPmMut4gcBJPacNztPb4TS2X3PnFQ/VKEyDKA9gX7UHL2kKBidRP4BsFN4B6XVp4O946dmZ2cUmUzMfwcivh8jClDqJ3BaiYaNWMlkv8VE5DwqJSDVE/giWgN+AkSUx00pwkbOVMd8AWcSA6jVnOcpC4/jRRC34ENMYXjAQ/vQ9TjQQS366YFDazegYRXoElIZ7y/IoEitJOyKLJ/Akku9ARkjpWp1kGupo9g1ei0WIX369BBqf8VE2siBcy6VtptNxVsl0PiivX3KJPJxz6EtE1uk8SGsBt8rFymVsR6C5+wJLN9lLXyWQhljFTpA6RfBjWZMe68o/5T1DiQsvrbCesH1YvxilHR+ZptdlFKjplSmfgcMpUuxQkhMQbk92GCtkdKGsLBpAKjSvt+S5tPEnUEnZgXtelHZ2wBW6FUYMYBJlwNV+kSImrGDYbNaa6Oh7cbtxXvA5E0aNcWi1n4H3IIT7DZErHEFa+dcAPDO+PqsHA5E30/iZMiOvcFrSjkla3EmsHC5Hz1BrcmNLmAKWr8AtLEECMsQ0YWyo6H6LlMtDmpJAbfJbEM+Z+oLeOycQYBgBZYPvB8RpZRKKTkKMk04vPU78Dgq7pNNC8akXjiHPUf0hESS1KSC6w6BfgMePfhtwzXBuJChYOOmfAKRUR3SObWnvQBwq9XYgXxxHmLELVMQyJYwreMLQDH6CRzFb7hMjXHpjAUSlJGDYM5Be51/LuNhDUNa0c6kvbcedcoZGBxH3/8Cdr+uuH09AAYUC66MjIVxvl874RfQQX9sIYRRPow+pxgDVvtri/wCHlUra9fN+YApp5BGHW2sv8/vF3DEZREas0Y3GFcK24fy+b6nPu0CHt2J93e9RVwDGH5cP951Suc++xvYo5XyY42n/CmBVsIPEDvrh5cB9ORwOle9bihSWMO2Gfw7xxRx8mJr171xAXtyEmeRBxjKWo0bQeE46xwhAx0XR213hghGzwslQlhXI9jMsKUWjTrlLM4BsmU/A3sauYxhD4VtxZaduVhsyr6Ua1VOXOhQW/0OUAUxQcAmXxZtU3TX+y+bTG054Z3ZXo8kYNibUUbjBe2yY+RuFO/ImeGWuD/CUfDWOY+ltqjDX8bs16/ndcZRH2O1mCn5H5tf55//ZeBFSy/+T5vIPxr9Z+A/SGudprzcys0AAAAASUVORK5CYII=");
        }
        .mosqueteroweb{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEUDBQEQEQ4hGRIaGxkqGQkyJRonKCY/Kxc0NjQ/NSxCQ0FfQiJZRzNRU1BgYmCDXTJ9alVucG2NfWeAgn+jhF6PkI2hj3zjjTWfoZ6tn47BrJaxs7DCw8DXwqTR1NH4+velZzBdAAAAAWJLR0QAiAUdSAAAAAlwSFlzAAAOxAAADsQBlSsOGwAAAAd0SU1FB+EFBQopGlpB/oIAAASVSURBVEjHXVXbYusoDBQWBoyBmFBSElP3//9yR9jp2VYPCQaNLiMhyDjnITHX1vZ97/3orabxWVJpreYk587n7J0zihgILIzzOBZA73uLsFAEUHPEGcSnnPDHRGaoi7hYTh97hkVXWo0pDX1mk0qJxvvhwUfvhg3oi4Nek0OITXA5ny48fOHLsyJlUkWcCFq0D0jPUC91B86liiQi4qtw4CJ8DQDy+6cvgNZz2auHSq4wF8WmZxdZAcAGoXqfBDEAR0t7dbGWQY+PEpOXbDw8KDJKKYaMnIWivhco4zSlXLI3PMT4ih2hFW4GQmhKYKmWkuJeQR6+JfILkAqnjD0aTPPFao8OyUakBeKkMohLjplLrxwTiKW2gwfQHgtyKIrycey17YOoUkqtBaV2prbiGJVg2kVaLqMpPHEsI29/VrENQRQF+gyvbgBaQZ2EokxiAswipNhGmwxz3pTmwAvCBEAqI90HSDWVFf6hgm4bCJAGpmJvXnGMOVI92RZJFRAibqIjNElYoACS4FMpFMej+f4BUHFDRHGQKWybjP4IYTHAepZPg9YYyujZ2I+EShKj4VBShVYAU/fQj+1mfEMCeRh0g1UfRGwIaHhkiQb292Dnbatfn5/N3NozGNS1ORhE4ycov76+gmWypHJHVZegH18b1Ruvn5/L/phwEaQYCBkdsAXp1d35akmTgx2rtekT3REima3352SZfc0ICY0U7EliQ+yatPfKWqV8o0X09d6P/U7YMTkzupXsPMsoSO25PBI8WGNnspJPPSrTdAOpQTlWYNQR7sQSonDlwkxbJKXmVcPxatdbbfAwhVt7KMvzPGEGEDpRbbhHUo6ogqfZkl0h1ix2aoVgRrmAPQXnkpFxSlNAIi4+Z63CvNJqrV0nG27LsehXX7aorZk0TQJA6dW6fJOb1q2HyWp42EAesCvdgv14hEd/0TThUxtvCO0w+SPvyry+9qC0tloASGNab7ewlAdu7UaP4iaL4YQL1NrC399HBtm7VTzD78ZAkZ2OD/Xq/bHtdN/3j0kGZwSgzuS/v3tAByMZLbQsok/3r4dCPW3/wCV46pldFgCqp4E4ll6kBiB0XvErVG127q/w7NPHC8sxCwxlhEVaT95ujbUGazxbocOiFyyF8NwfWM88xoeSTpLy06T1kh0iyVHZsTN2bcDou+NCiHW5I6gDv0/ZYSkzRS4RuYjgcIUwkdyYWuNKCcCZNwJDRwppjHgoGSbGrM7yMvCpLyFl99aPY2WyG/dOXW5jkplvlLoAPl4xccznotYxPgdYXif/fwhR8pe+yVeuMvK8GVzgnUoRkkQGhAn/YkrG+Tu0XGSmAqAwvpGBgC4I7gMerAFAZhdAjWkh/jAgBYF48IgAiUnDCH3EhFke3wB2YlMSvxAljhjMmZc/LSuMwbFCoEbmvZwqL4AkBSJ3pcj+bRhPcfTmfIzjmCfDGQA/tRWJPwCFOCWzYe6yJ+7iT3YnJz+Ncx6emu4yekb9y8OvD2Sk/im+//mXhz/60Rv1Z1P99vD7SIaN+3N+tcnbDv9fzGgeZ/5sXn+jZf8D5vFZIZ+pzf0AAAAASUVORK5CYII=");
        }
        .podcastlinux{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEW6Sg27URzJYBnAZjrKaS/LfErLhWPZmV7Vm2/SnHngrH/csY/auKTJy8jZyL3gybfhyL/ez8vf0cXS1NHm2N/b3Nnl29Lc3+Lh4d7s49zl6Ovn6ebt8O3y9PH4+vf9//xpIPITAAAAAWJLR0QAiAUdSAAAAAlwSFlzAAAN1wAADdcBQiibeAAAAAd0SU1FB+EFBQosLgaC/nIAAABBdEVYdENvbW1lbnQAQ1JFQVRPUjogZ2QtanBlZyB2MS4wICh1c2luZyBJSkcgSlBFRyB2NjIpLCBxdWFsaXR5ID0gODIKg7FQJgAAApdJREFUSMe1lguzmjAQhUNRL5BISriQlWTj//+X3c1DENS2M+1BYQbPx9k8SBT3v5T4F0AgISKd/whg76rwGyCg9xs3J4UPANtZiIWKgeEdkO2ZKQTdx9fA1l+CfHz8NuQBBO9IByS1O6yEePIfCR9iRcHvgew/QuH+TGQA3U5rRiFwCwR31NqMRORmiLUgpGE4IiE66ZuLEo+CAp0RDymrOw2HKAHJusugGzQVadwDu30BYgswufetp3uP7oqtEKUidBzuEN41H1NHMZAeBTHLOyC5xS30eUYwRohcEdCgEorRD7DM823Zx2AGUtngeSJnv13akzrrPfIA6IfoSnZLBwGEcFWpuKjYxwT45bbAYgG0YTd/NDQnJXtttIJB3Zw2SrtvNWMCwBhrDMydHoZ5MEabs6SEH+3pVImLEtpVzaVSdWUyoL+aTtLRdI1su6ZppDQJqHV9UlV/qy63mllTgK6TRDRfUn8p8jdSNxFoF3qy6F3Vuouo6lqlRpvOgFQg5dQpo6SWWhfAMtBK0aqqFpcllYSzsdxFjjvDsiZr27M8tefWNvVc06Mv9flGbB44S/1CHTux6GL5OvSmH/RIVxioL/p+WODnkIB7nAxTlucTMTlpmif7zX0dH5oBD8A2uhEzIjHGoHlKeTYOj13K9I4BjAeqy42kgY4puzNDRJmtd0cApMVgGmF8VqmV6l5fUQJcWg2m0Y1viOnxxlEl/gNQENisGhwRX3H3yp8R3C5kPAyeXqURpvGN3PNSCWngIDX5Soqn65oRdosxjx7n+uxcNUYKD8t9qgXd9ZXGcNxQEnE9BEQ/vtqBgivl7wXhzaaIL+1X/2HbdUcEPm/swcOGGeOU/N1fB1rQ0nrpMfynPycf9QuEruKuulaDHwAAAABJRU5ErkJggg==");
        }
        .salmorejogeek{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEUcGxwmJSgiJzQ2NTM3RVQ9VYJuUShYVlNEZlJGY8BdZm5IartvcnFQdv9SfrxTfP9Whv+Hhn6Ck51hmP/gkzZpqv9wtv61tKp5v/1k2YjovEvYxHnDxcK60uTy5b3x69cOzPdIAAAAAWJLR0QAiAUdSAAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB+EFBQoyB5BxWcEAAAHiSURBVEjHldTrmqMgDAbgcCpbZT12prP24P3f5SRKEAWfsl9/1eZtCNDCuOYrl2/OzxYY/1ME8EF8p6BQRCBPjmIHSsQeFIi0Q9MY0zSnm3WYwUjQFUaDNPkeMWiMqoaXz1Ap02REBIwO1d5ok4oNCPdK4mQiGNRieGUyiOOyPKhVtj4joOuW9ZzUY+R+s1Yg1/UPlGQOvRMIutHY5RMlAECo4/DW/GAhiwVIeq6ED6ituAIfwz0I1BUNtwWE48VVf3z4RJYZ6MCUiLN+K+6E++cTjpA6iGP9kuWaBKAjUFtcqqDX1oEvVRYYhwNcbrfLVl+FPc0BOViqv91C/XYWeeBAUf10gXXg6OzyQAA1mKZJ4dbYvrcZYHaABNZPD9s/3u93Xw0cGzo0/meLQAOd1QXrH1T+nmelrI9igE+U4V1a91OF+rl3T5+wJHziGNT+AOC+ln8AbdfxiaGYC0DLaxLCzkWgvYZLcT8Cy7d1BzrNa+qPoOKv2oHQIgVxIhCmcIWg7STEU5+CkUFL96OgA/7BeNBeqQeUgL9e0Bwfh14Ai7YGuBeB0KMz0t2fT/xBWLemX+LfWLziK4jI1RgN5xEMwrLQ4BafRgawCSKUMc0Xz0D1qdiyU6FDqWBwmONc/AL0UaQcBFX61wAAAABJRU5ErkJggg==");
        }
        .ugeek{
            background-image: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAwCAMAAABg3Am1AAAAYFBMVEVVMZZcL5ljMJVdM5VlMphnNJllNpNtNpdxOZt4PJiCPZ2KQZ2RRJyYRJ+gSJ+oTJ6vTKK3UaK/UKXFVKPOVKjMWaPVWajcWKrbXKXkXarqYKjyYKz1Y67/ZK76Zqz+aq9CAXa/AAAAAWJLR0QAiAUdSAAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB+EFBQorIK57RbIAAAF5SURBVEjH7ZVhc4MgDIYrHEMEI5rikEr8//9ytLVrxR12X3d7T4RwPJhwJJ7YL3X6SwDXRckcgLjEkpZBbABNh7IbAAl4yfMq7fgKVCHqbImQG1Mui3wFptjcBsp7dV9R+xz4yAHVKO2lrGtn2DDIUbcHQKs19HxAp6YOLAbkbwCOC/QAPVgT8Mgl6Zxs3aiNQ+WcQdOLMsCqam337jDox3k+9oWXMy4AYoJRpXC59BXnLD1VGhaBUweTV3im2o96DDZ4S6oAfAbEhuEoPEiGAqxHGcpfYIDQTpq0NZ1xQ4f9pRS0Sa0FVvfAAVjXKug4lICfJSkDCIeydkA80A4Y+q1sZmZAyGOYqBhDStFObNSft7ahmb8CTcryjcd7G7ZlRoflKYrXd7x36xTkheyUcnOVitPVwGi/5xQvlUoXb8nWRnqvtipabpWDX8i8BYw0rLcqknwD8M9lY7zIA2Ca54Xmhy4Uk6FKgJ93CnXZJbHTH/4p/gMFfQHdIENuISGquQAAAABJRU5ErkJggg==");
        }
        body{
            background-color: rgb(247, 247, 247);
            font-family: "Roboto", sans-serif;
            body { background-image:
            background.image: url("data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='10' height='10'><linearGradient id='gradient'><stop offset='10%' stop-color='%23F00'/><stop offset='90%' stop-color='%23fcc'/> </linearGradient><rect fill='url(%23gradient)' x='0' y='0' width='100%' height='100%'/></svg>");
      }
        }
        .panel{
            webkit-box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            -moz-box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            box-shadow: 0 0 1px rgba(0, 0, 0, 0.15);
            box-sizing: border-box;
            display: block;
            min-height: 70px;
            background-color: #fff;
            padding: 10px;
            margin: 0 auto;
            margin-bottom: 20px;
        }
        audio {
            width:250px; /* Ancho del reproductor */
            display: block;
            float:left;
        }
        ul {
          list-style-type: none;
          padding-left: 0px;
        }
        li {
            list-style-type: none;
            height:70px;
        }
        span[id^="item-"]{
            height:48px;
            line-height: 20px;
            display: block;
            }
        .isplaying{
            float:left;
            margin-top:12px;
            width:24px;
            height:24px;
            margin-right: 5px;
        }
        .logo{
            float:left;
            width:48px;
            height:48px;
            margin-right: 5px;
        }
        .podcast, #podcast{
            display: block;
            font-size: 16px;
            font-weight: 400;
            color:rgba(0,0,0,.87);
            }
        .track, #track{
            display: block;
            font-size: 14px;
            font-weight: normal;
            color:rgba(0,0,0,.54);
        }
        #track{
            text-overflow: ellipsis;
            display: -webkit-box;
           -webkit-box-orient: vertical;
           -webkit-line-clamp: 2;
        }
        #player{
            height:80px;
            float:left;
        }
        #playing{
            height:80px;
            float:left;
        }
        .playingnow{
            font-size: 12px;
            color: #9E9E9E;
        }
        a{
            text-decoration:none;
            color:rgba(0,0,0,.54);
        }
        a:visited{
            text-decoration: none;
            color:rgba(0,0,0,.54);
        }
        @media only screen and (min-width: 700px) {
            .panel{
                width:600px;
            }

        }
    </style>
</head>
<body>
    <div class="panel">
        <div id="player">
            <a href="#" id="left" onclick="return false" title="Anterior">
                <i class="fa fa-chevron-left" aria-hidden="true"></i>
            </a>
            <audio id="audio" preload="auto" tabindex="0" controls="">
                <source src="">
            </audio>
            <a href="#" id="right" onclick="return false" title="Siguiente">
                <i class="fa fa-chevron-right" aria-hidden="true"></i>
            </a>
        </div>
        <div id="playing">
            <span class="playingnow">Reproduciendo ahora...</span>
            <span id="podcast"></span>
            <span id="track"></span>
        </div>
    </div>
    <div class="panel">
        <ul id="playlist">

<li class="active">
	<span id="item-0">
		<a href="https://ia601506.us.archive.org/33/items/JekyllOWordpress/Jekyll%20o%20Wordpress.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">052. ¿Jekyll o WordPress?</span>
		</a>
	</span>
</li>
<li>
	<span id="item-1">
		<a href="https://ia801502.us.archive.org/5/items/051.AdisBloggerHolaGithub/051.%20Adi%C3%B3s%20Blogger,%20Hola%20Github%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">051. Adiós Blogger, Hola GitHub!</span>
		</a>
	</span>
</li>
<li>
	<span id="item-2">
		<a href="https://ia801505.us.archive.org/9/items/050.QueAndoHaciendo/050.%20Que%20ando%20haciendo.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">050. Que ando haciendo, nuevas publicaciones y más...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-3">
		<a href="https://ia601503.us.archive.org/0/items/049.Syncthing/049.%20Syncthing.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">049. Instalando Syncthing en Ubuntu, Antergos y Raspberry Pi</span>
		</a>
	</span>
</li>
<li>
	<span id="item-4">
		<a href="https://ia601503.us.archive.org/28/items/EncuentroDeAmiguetes/Encuentro%20de%20amiguetes.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">048. Encuentro de amiguetes</span>
		</a>
	</span>
</li>
<li>
	<span id="item-5">
		<a href="https://ia801500.us.archive.org/21/items/SeEstropeaLaSDDeMiRasberry/Se%20estropea%20la%20SD%20de%20mi%20rasberry.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">047. Se quemó la SD. Comparación de consumos entre PC, NAS-Microserver, Raspberry Pi</span>
		</a>
	</span>
</li>
<li>
	<span id="item-6">
		<a href="https://ia601509.us.archive.org/6/items/046SyncthingResilioYDukto/%23046%20Syncthing%2c%20Resilio%20y%20Dukto%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">046. Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto</span>
		</a>
	</span>
</li>
<li>
	<span id="item-7">
		<a href="https://ia801502.us.archive.org/1/items/041UbuntuYElAdiosAUnity/%23041%20Ubuntu%20y%20el%20adi%c3%b3s%20a%20Unity.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">041. Ubuntu y el adios de Unity</span>
		</a>
	</span>
</li>
<li>
	<span id="item-8">
		<a href="https://ia801505.us.archive.org/27/items/045CrossoverConSalmorejoGeek/%23045%20Crossover%20con%20Salmorejo%20Geek.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">045. Crossover con Salmorejo Geek, donde hablamos de Mastodon, Ubuntu, Telegram y mucho mas...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-9">
		<a href="https://ia801504.us.archive.org/22/items/044WebDeJekyllEnGithub/%23044%20Web%20de%20Jekyll%20en%20Github.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">044. La web de Jekyll en GitHub, va tomando forma</span>
		</a>
	</span>
</li>
<li>
	<span id="item-10">
		<a href="https://ia601509.us.archive.org/23/items/043BotDeTelegramDeIFTTT/%23043%20Bot%20de%20Telegram%20de%20IFTTT.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">043. Bot de Telegram IFTTT</span>
		</a>
	</span>
</li>
<li>
	<span id="item-11">
		<a href="https://ia601502.us.archive.org/25/items/042ElAtareaoVisitaElCrossoverDeLaSemana/%23042%20El%20Atareao%20visita%20el%20Crossover%20de%20la%20Semana.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">042. El Atareao visita el Crossover de la Semana</span>
		</a>
	</span>
</li>
<li>
	<span id="item-12">
		<a href="https://ia801504.us.archive.org/29/items/40AntergosOCNewsDeNextcloudYJekyll/%2340%20Antergos%2c%20OCNews%20de%20Nextcloud%20y%20Jekyll%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">040. Antergos, Ocnews De Nextcloud Y Jekyll</span>
		</a>
	</span>
</li>
<li>
	<span id="item-13">
		<a href="https://ia601508.us.archive.org/2/items/039TelegramNotes/%23039%20Telegram%2c%20Notes.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">039. Aplicación Notes de Nextcloud y crea tus bots de Telegram</span>
		</a>
	</span>
</li>
<li>
	<span id="item-14">
		<a href="https://ia601506.us.archive.org/26/items/38CrossoverConMosqueteroWeb/%23%2038%20Crossover%20con%20MosqueteroWeb.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">038. Crossover con MosqueteroWeb. Masterclass de FreeNas, Docker y virtualización mediante Proxmox y Esxi.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-15">
		<a href="https://ia801503.us.archive.org/18/items/037LlamadasDeTelegram/%23037%20Llamadas%20de%20Telegram.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">037. Llamadas de Telegram ya estan aquí. Y 3 bots que os encantaran</span>
		</a>
	</span>
</li>
<li>
	<span id="item-16">
		<a href="https://ia601509.us.archive.org/25/items/036PodcastConFrank/%23036%20podcast%20con%20Frank.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">036. Podcast con Frank de Batería2x100, Servidores Linux y NAS, lo mismo pero  diferente</span>
		</a>
	</span>
</li>
<li>
	<span id="item-17">
		<a href="https://ia601501.us.archive.org/10/items/035MiG8/%23035%20Mi%20G8.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">035. Mi HP ProLiant MicroServer Gen8</span>
		</a>
	</span>
</li>
<li>
	<span id="item-18">
		<a href="https://ia801500.us.archive.org/9/items/034BotDeTelegramSustitutoAShazam/%23034%20Bot%20de%20Telegram%20sustituto%20a%20Shazam.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">034. Bots de Telegram Sustitutos a Shazam y busqueda de articulos dentro del bot de Pocket</span>
		</a>
	</span>
</li>
<li>
	<span id="item-19">
		<a href="https://ia601500.us.archive.org/4/items/033BotDePocketParaTelegram/%23033%20Bot%20de%20Pocket%20para%20Telegram.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">033. Bots en Telegram. Bot de Pocket</span>
		</a>
	</span>
</li>
<li>
	<span id="item-20">
		<a href="https://ia601606.us.archive.org/30/items/032MiscelaneaDeViernes/%23032%20Miscel%C3%A1nea%20de%20Viernes.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">032. Miscelánea de Viernes</span>
		</a>
	</span>
</li>
<li>
	<span id="item-21">
		<a href="https://ia601606.us.archive.org/14/items/031Keepass.ComoGestionoMisContrasenas/%23031%20Keepass.%20Como%20gestiono%20mis%20contrase%C3%B1as.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">031. Keepass, como gestiono mis contraseñas</span>
		</a>
	</span>
</li>
<li>
	<span id="item-22">
		<a href="https://ia601609.us.archive.org/0/items/030Mumble/%23030%20Mumble.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">030. Mumble, VoIP de Software Libre. Nextcloud, Wallabag y kdenlive</span>
		</a>
	</span>
</li>
<li>
	<span id="item-23">
		<a href="https://ia601608.us.archive.org/28/items/029MiscelneaDeViernes/%23029%20Miscel%C3%A1nea%20de%20viernes.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">029. Miscelánea de Viernes.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-24">
		<a href="https://ia601607.us.archive.org/17/items/ugeekpodcast_gmail_XMPP/XMPP.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">028. Instala un servidor de mensajeria tipo Whatsapp o Telegram y de Software Libre con XMPP/Jabber</span>
		</a>
	</span>
</li>
<li>
	<span id="item-25">
		<a href="https://ia601606.us.archive.org/3/items/027InstalaTuVpnEnUbuntuORaspberryPi/%23027%20instala%20tu%20vpn%20en%20Ubuntu%20o%20Raspberry%20Pi.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">027. Instala una VPN (OpenVpn) en Ubuntu o Raspberry Pi con PiVpn</span>
		</a>
	</span>
</li>
<li>
	<span id="item-26">
		<a href="https://ia601606.us.archive.org/25/items/026PodcastConFrankDeBatera2x100/%23026%20Podcast%20con%20Frank%20de%20Bater%C3%ADa2x100.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">026. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestras Fotos, actualidad y sorteo del libro del año</span>
		</a>
	</span>
</li>
<li>
	<span id="item-27">
		<a href="https://ia601600.us.archive.org/16/items/025MtodoMMsCompletoQueParaRecopilarNotasOrgMode/%23025%20M%C3%A9todo%20m%C3%A1s%20completo%20que%20para%20recopilar%20notas%2C%20org%20mode.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">025. Metodo mas completo para recopilar notas, org Mode</span>
		</a>
	</span>
</li>
<li>
	<span id="item-28">
		<a href="https://ia601605.us.archive.org/10/items/024ConectateRemotamenteATuRaspberryPiCondataplicity/%23024%20Conectate%20remotamente%20a%20tu%20Raspberry%20Pi%20con%20%22dataplicity%22%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">024. Conectate remotamente a tu Raspberry Pi con "dataplicity"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-29">
		<a href="https://ia801609.us.archive.org/20/items/EntrevistaADosDesarrolladoresDeSoftwareLibreDeIgalia/Entrevista%20a%20dos%20desarrolladores%20de%20Software%20Libre%20de%20Igalia.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">023. Entrevista a Chema y Juan, dos desarrolladores de Software Libre de Igalia.com en el #mwc17</span>
		</a>
	</span>
</li>
<li>
	<span id="item-30">
		<a href="https://ia601600.us.archive.org/33/items/EntrevistaConArturoSuarezDirectivoDelCloudDeCanonicalUbuntu/Entrevista%20con%20Arturo%20Suarez,%20Directivo%20del%20Cloud%20de%20Canonical%20Ubuntu.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">022. Entrevista con Arturo Suarez, DIrectivo del Cloud de Canonical Ubuntu</span>
		</a>
	</span>
</li>
<li>
	<span id="item-31">
		<a href="https://ia801606.us.archive.org/21/items/021UbuntuEnMobileWorldCongress/%23021%20ubuntu%20en%20Mobile%20World%20Congress%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">021. Ubuntu en el Mobile World Congress</span>
		</a>
	</span>
</li>
<li>
	<span id="item-32">
		<a href="https://ia601601.us.archive.org/7/items/20PodcastConFrankDeBatera2x100HablamosDeComoGestionamosNuestraNotas/%2320%20Podcast%20con%20Frank%20de%20Bater%c3%ada2x100%2c%20Hablamos%20de%20como%20gestionamos%20nuestra%20notas%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">020. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestra notas y mucho mas...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-33">
		<a href="https://ia601603.us.archive.org/6/items/019DokuwikiNuevaFormaDeTomarMisNotas/%23019%20Dokuwiki%2c%20nueva%20forma%20de%20tomar%20mis%20notas%20.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">019. Dokuwiki, nueva forma de tomar mis notas. Monta tu wiki con DokuWiki o MediaWiki.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-34">
		<a href="https://ia601604.us.archive.org/24/items/018WallabagElPocketOInstapaper/%23018_Wallabag%2c_el_Pocket_o_Instapaper.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">018. Como montar Wallabag, el Pocket o Instapaper de software libre y lo mejor de todo, en tu servidor</span>
		</a>
	</span>
</li>
<li>
	<span id="item-35">
		<a href="https://ia801300.us.archive.org/34/items/017PodcastConFrankDeBateria2x100HablandoDePlexNextcloud.../%23017%20Podcast%20con%20Frank%20de%20Bateria2x100%2c%20hablando%20de%20Plex%2c%20Nextcloud....mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">017. Podcast con Frank de Bateria2x100, hablando de Plex, Nextcloud...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-36">
		<a href="https://ia801603.us.archive.org/24/items/016QueEsUnServidor/%23016%20Que%20es%20un%20servidor.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">016. Que es un Servidor (dudas oyentes), servidor web, ...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-37">
		<a href="https://ia801603.us.archive.org/20/items/015AlmacenamientoTheNextcloud/%23015_almacenamiento_the_nextcloud.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">015. Como ampliar el almacenamiento de Nextcloud, combinar con nubes publicas y hacer copias de mis fotos.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-38">
		<a href="https://ia601602.us.archive.org/11/items/NotasEnNextcloud/Notas%20en%20nextcloud.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">014. Notas en Nextcloud y Markdown</span>
		</a>
	</span>
</li>
<li>
	<span id="item-39">
		<a href="https://ia801601.us.archive.org/21/items/013NewsYFreshRSS.GestorDeNoticiasRSS/%23013%20News%20y%20Fresh%20RSS.%20Gestor%20de%20Noticias%20RSS.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">013. News y FreshRSS. Gestor de Noticias RSS.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-40">
		<a href="https://ia801604.us.archive.org/21/items/013FDroidAplicacionesDeSoftwareLibre/%23013%20F-Droid%20Aplicaciones%20de%20Software%20Libre.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">013. bis F-Droid Tienda Android de aplicaciones de Software Libre y Actualizar las Noticias en Nextcloud.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-41">
		<a href="https://ia801601.us.archive.org/24/items/012CmoActualizarNextcloudY/%23012_c%c3%b3mo_actualizar_Nextcloud_y.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">012. Como actualizar Nextcloud y salir del modo de "mantenimiento"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-42">
		<a href="https://ia801602.us.archive.org/16/items/011PodcastConFrankDeBateria2x100/%23011%20Podcast%20con%20Frank%20de%20Bateria2x100.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">011. Podcast con Frank de Bateria2x100, hablando un poco de todo...</span>
		</a>
	</span>
</li>
<li>
	<span id="item-43">
		<a href="https://ia601603.us.archive.org/9/items/010ElSistemaOperativoDeBolsillo/%23010%20El%20Sistema%20Operativo%20de%20bolsillo.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">010. CloudReady el Chromium OS de bolsillo</span>
		</a>
	</span>
</li>
<li>
	<span id="item-44">
		<a href="https://ia601602.us.archive.org/11/items/ComoCrearTuPodcastYTotalmenteGtatis/Como%20crear%20tu%20podcast%20y%20totalmente%20gtatis.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">009. Crea tu podcast en 3 simples pasos y totalmente gratis</span>
		</a>
	</span>
</li>
<li>
	<span id="item-45">
		<a href="https://ia801900.us.archive.org/13/items/008ComoGestionoMisNotas/%23008%20Como%20gestiono%20mis%20notas.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">008. Como gestiono mis Notas</span>
		</a>
	</span>
</li>
<li>
	<span id="item-46">
		<a href="hhttps://ia601902.us.archive.org/28/items/007LinuxEsUnaAlternativaReal/%23007%20Linux%20es%20una%20alternativa%20real.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">007. Linux es una alternativa real</span>
		</a>
	</span>
</li>
<li>
	<span id="item-47">
		<a href="https://ia601900.us.archive.org/18/items/ElTrelloDeSoftwareLibreWekan/El_Trello_de_software_libre_Wekan.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">006. El Trello de Software Libre Wekan y Kanboard para Raspberry Pi. El sistema Kanban en tu servidor.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-48">
		<a href="https://ia601603.us.archive.org/9/items/005PaperDeDropbox/%23005%20Paper%20de%20Dropbox.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">005. Paper de Dropbox</span>
		</a>
	</span>
</li>
<li>
	<span id="item-49">
		<a href="https://ia601903.us.archive.org/19/items/004ServidorLinuxVsQNapSynology/%23004%20Servidor%20Linux%20Vs%20QNap-Synology.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">004. Servidor Linux Vs QNAP-Synology</span>
		</a>
	</span>
</li>
<li>
	<span id="item-50">
		<a href="https://ia601903.us.archive.org/4/items/003Nextcloud/%23003%20Nextcloud.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">003. Nextcloud. Instalar tu Nube en menos de 2 minutos.</span>
		</a>
	</span>
</li>
<li>
	<span id="item-51">
		<a href="https://ia801904.us.archive.org/20/items/DeQueVaEstoDeUGeek/De%20que%20va%20esto%20de%20uGeek%3f.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">002. "De qué va esto de uGeek?"</span>
		</a>
	</span>
</li>
<li>
	<span id="item-52">
		<a href="https://ia801602.us.archive.org/21/items/HolaMundo_201701/Hola%20Mundo.mp3">
			<span class="isplaying"></span>
			<span class="logo ugeek"></span>
			<span class="podcast">uGeek</span>
			<span class="track">001. Hola Mundo</span>
		</a>
	</span>
</li>
        </ul>
    </div>
</body>
</html>
