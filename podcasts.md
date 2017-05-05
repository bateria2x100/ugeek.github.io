---
layout: page
title: "Podcast de Linux"
desc: "Lista de post ordenados por etiquetas"
permalink: /podcasts/

sitemap:
  priority: .5
---
[desarrollado por atareao.es](https://www.atareao.es/)

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
    var ntracks;
    function initaudio(){
        audio=$("audio");
        playlist=$("#playlist");
        ntracks=$("[id^=item-]").length
        audio[0].volume=1;
        current=0;
        current_pista=playlist.find("#item-0");
        runaudio($(current_pista),audio[0]);
        $("[id^=item-]").click(function(e){
            e.preventDefault();
            link=$(this);
            current=link.parent().index();
            runaudio(link, audio[0]);
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
        current++;
        current_pista=playlist.find("#item-"+current);
        if(current_pista.length==0){
            current=0;
            current_pista=playlist.find("#item-0");
        }
        runaudio($(current_pista),audio[0]);
    }
    function playprevious(){
        current--;
        current_pista=playlist.find("#item-"+current);
        if(current_pista.length==0){
            current=ntracks-1;
            current_pista=playlist.find("#item-"+current);
        }
        runaudio($(current_pista),audio[0]);
    }
    function runaudio(item,player){
        title=$(item.find(".title"));
        $("#podcaster").text(title.text());
        link=$(item.find("a"));
        episode = link.text()
        if(episode.length>33){
            $("#episode").text(link.text().substring(0,30)+"...");
        }else{
            $("#episode").text(link.text());
        }
        player.src=link.attr("href");
        par=link.parent();
        par.addClass("active").siblings().removeClass("active");
        audio[0].load();
        audio[0].play();
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
    <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
    <style>
        #left{
            background: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAgCAYAAAAbifjMAAAAl0lEQVRIx+3UMQoCMRRF0aO1VloKdroM3YvgSsRdiJ2uwkYstRbciVVsZmAMMmYmbS6EVO9+Ql5CodCNMc549AkvcUGoVhKDal/j1QiHLpO3eEfhkDp9/yOYJJji2BJuFcxx+xNuFTwTwl+CYSQIuWWZ4ZpzBJjgkCOor3GXI6jZ9C1Ss8qrnCrXLPo8ppgRTriXn60Q8wECX1R63JgTcwAAAABJRU5ErkJggg==");
            float: left;
            width: 16px;
            height: 32px;
            cursor:hand;
        }
        #right{
            background: url("data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAgCAYAAAAbifjMAAAAjUlEQVRIx+3UOwoCQRCE4W+NNdJQMNNj6F0ETyLeQsz0FJuIoaYG3mSjNtlgQRDtSaegkoH+KaYfVFV96o4zxllA9G6xLAEEXlj3700GEOiwzSYYev9rivjiI6YlgMAV8xJA4DksGCU61ZQkuGGRBZwwy37iIdvGDruSUd5kR7nFKrNMD1wwqZet6h+9AfPLU3sbivmUAAAAAElFTkSuQmCC");
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
            width:300px; /* Ancho del reproductor */
            display: block;
            float:left;
        }
        ul {
          list-style-type: none;
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
        .logo{
            float:left;
            width:48px;
            height:48px;
            margin-right: 5px;
        }
        .title{
            display: block;
            font-size: 18px;
            }
        .mp3, #episode, #podcaster{
            display: block;
            font-size: 14px;
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
            <a href="#" id="left" onclick="return false" title="Anterior"></a>
            <audio id="audio" preload="auto" tabindex="0" controls="" autoplay>
                <source src="https://ia801502.us.archive.org/5/items/051.AdisBloggerHolaGithub/051.%20Adi%C3%B3s%20Blogger,%20Hola%20Github%20.mp3">
            </audio>
            <a href="#" id="right" onclick="return false" title="Siguiente"></a>
        </div>
        <div id="playing">
            <span class="playingnow">Reproduciendo ahora...</span>
            <span id="podcaster">uGeek</span>
            <span id="episode">Title</span>
        </div>
    </div>
    <div class="panel">
        <ul id="playlist">


<li class="active">
<span id="item-0">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801502.us.archive.org/5/items/051.AdisBloggerHolaGithub/051.%20Adi%C3%B3s%20Blogger,%20Hola%20Github%20.mp3">051. Adiós Blogger, Hola GitHub!</a>
</span>
</span>
</li>
<li>
<span id="item-1">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/05/podcast-26-odoo-y-transformacion.mp3">Podcast #26: Odoo y transformación digital</a>
</span>
</span>
</li>
<li>
<span id="item-2">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/119-geekeando-erika-betancor_mf_18422071_feed_1.mp3">#119 Geekeando con Érika Betancor</a>
</span>
</span>
</li>
<li>
<span id="item-3">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801505.us.archive.org/9/items/050.QueAndoHaciendo/050.%20Que%20ando%20haciendo.mp3">050. Que ando haciendo, nuevas publicaciones y más...</a>
</span>
</span>
</li>
<li>
<span id="item-4">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/118-directo-asi-estan-cosas-abril-2017_mf_18412331_feed_1.mp3">#118 Directo: Así están las cosas (Abril 2017)</a>
</span>
</span>
</li>
<li>
<span id="item-5">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601503.us.archive.org/0/items/049.Syncthing/049.%20Syncthing.mp3">049. Instalando Syncthing en Ubuntu, Antergos y Raspberry Pi</a>
</span>
</span>
</li>
<li>
<span id="item-6">
<span class="logo compilandopodcast"></span>
<span class="title">Compilando Podcast</span>
<span class="mp3">
<a href="http://compilando.audio/wp-content/uploads/2017/04/podcast4.mp3">Podcast 4 – Jon “maddog” Hall , Open South Code y Linux y Tapas</a>
</span>
</span>
</li>
<li>
<span id="item-7">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601503.us.archive.org/28/items/EncuentroDeAmiguetes/Encuentro%20de%20amiguetes.mp3">048. Encuentro de amiguetes</a>
</span>
</span>
</li>
<li>
<span id="item-8">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/twitter-sabemos-usarlo-android-audio-pocket-casts_mf_18349090_feed_1.mp3">Twitter, ¿sabemos usarlo? Android Audio y Pocket Casts</a>
</span>
</span>
</li>
<li>
<span id="item-9">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/23-la-terminal_mf_18347303_feed_1.mp3">#23 La Terminal</a>
</span>
</span>
</li>
<li>
<span id="item-10">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801500.us.archive.org/21/items/SeEstropeaLaSDDeMiRasberry/Se%20estropea%20la%20SD%20de%20mi%20rasberry.mp3">047. Se quemó la SD. Comparación de consumos entre PC, NAS-Microserver, Raspberry Pi</a>
</span>
</span>
</li>
<li>
<span id="item-11">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/117-sin-sombra-helicoptero_mf_18309317_feed_1.mp3">#117 Sin sombra en el helicóptero</a>
</span>
</span>
</li>
<li>
<span id="item-12">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/116-conociendo-deepin-gnu-linux-15-4_mf_18295101_feed_1.mp3">#116 Conociendo Deepin GNU Linux 15.4</a>
</span>
</span>
</li>
<li>
<span id="item-13">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-25-introduccion-a-docker.mp3">Podcast #25: Introducción a Docker</a>
</span>
</span>
</li>
<li>
<span id="item-14">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601509.us.archive.org/6/items/046SyncthingResilioYDukto/%23046%20Syncthing%2c%20Resilio%20y%20Dukto%20.mp3">046. Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto</a>
</span>
</span>
</li>
<li>
<span id="item-15">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801502.us.archive.org/1/items/041UbuntuYElAdiosAUnity/%23041%20Ubuntu%20y%20el%20adi%c3%b3s%20a%20Unity.mp3">041. Ubuntu y el adios de Unity</a>
</span>
</span>
</li>
<li>
<span id="item-16">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-24-sobre-vlans.mp3">Podcast #24: Sobre Vlans</a>
</span>
</span>
</li>
<li>
<span id="item-17">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/seguridad-hardware-tu-servidor-casero_mf_18128440_feed_1.mp3">Seguridad por Hardware en tu Servidor casero</a>
</span>
</span>
</li>
<li>
<span id="item-18">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/115-crossover-ugeek-podcast-mastodon-ubuntu-y_mf_18112915_feed_1.mp3">#115 Crossover con uGeek Podcast: Mastodon, Ubuntu y comunidad Linux, Telegram y mucho más</a>
</span>
</span>
</li>
<li>
<span id="item-19">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/22-linux-connexion-osl-la_mf_18133189_feed_1.mp3">#22 Linux Connexion con la OSL de la Universidad de La Laguna</a>
</span>
</span>
</li>
<li>
<span id="item-20">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801505.us.archive.org/27/items/045CrossoverConSalmorejoGeek/%23045%20Crossover%20con%20Salmorejo%20Geek.mp3">045. Crossover con Salmorejo Geek, donde hablamos de Mastodon, Ubuntu, Telegram y mucho mas...</a>
</span>
</span>
</li>
<li>
<span id="item-21">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801504.us.archive.org/22/items/044WebDeJekyllEnGithub/%23044%20Web%20de%20Jekyll%20en%20Github.mp3">044. La web de Jekyll en GitHub, va tomando forma</a>
</span>
</span>
</li>
<li>
<span id="item-22">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/114-ubuntu-abandona-unity-convergencia-y_mf_18057325_feed_1.mp3">#114 Ubuntu abandona Unity y la Convergencia ¿Y ahora qué?</a>
</span>
</span>
</li>
<li>
<span id="item-23">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601509.us.archive.org/23/items/043BotDeTelegramDeIFTTT/%23043%20Bot%20de%20Telegram%20de%20IFTTT.mp3">043. Bot de Telegram IFTTT</a>
</span>
</span>
</li>
<li>
<span id="item-24">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-23-calcular-mascaras-de-red.mp3">Podcast #23: Calcular máscaras de red</a>
</span>
</span>
</li>
<li>
<span id="item-25">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/que-pasa-ubuntu-hablando-linux-con_mf_18041732_feed_1.mp3">¿Qué pasa con Ubuntu? Hablando de Linux con El Atareao y con uGeek</a>
</span>
</span>
</li>
<li>
<span id="item-26">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601502.us.archive.org/25/items/042ElAtareaoVisitaElCrossoverDeLaSemana/%23042%20El%20Atareao%20visita%20el%20Crossover%20de%20la%20Semana.mp3">042. El Atareao visita el Crossover de la Semana</a>
</span>
</span>
</li>
<li>
<span id="item-27">
<span class="logo compilandopodcast"></span>
<span class="title">Compilando Podcast</span>
<span class="mp3">
<a href="https://compilando.audio/wp-content/uploads/2017/04/Podcast_3.mp3">Podcast 3 – Entrevista con ” el atareao” y el nuevo rumbo de Ubuntu</a>
</span>
</span>
</li>
<li>
<span id="item-28">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801504.us.archive.org/29/items/40AntergosOCNewsDeNextcloudYJekyll/%2340%20Antergos%2c%20OCNews%20de%20Nextcloud%20y%20Jekyll%20.mp3">040. Antergos, Ocnews De Nextcloud Y Jekyll</a>
</span>
</span>
</li>
<li>
<span id="item-29">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-22-iptables-en-gnu-linux.mp3">Podcast #22: NAT en GNU/Linux</a>
</span>
</span>
</li>
<li>
<span id="item-30">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/113-offtopiqueando-ando-informatica-semana-santa-chuck_mf_17909300_feed_1.mp3">#113 Offtopiqueando ando: Informática, Semana Santa y Chuck Norris</a>
</span>
</span>
</li>
<li>
<span id="item-31">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601508.us.archive.org/2/items/039TelegramNotes/%23039%20Telegram%2c%20Notes.mp3">039. Aplicación Notes de Nextcloud y crea tus bots de Telegram</a>
</span>
</span>
</li>
<li>
<span id="item-32">
<span class="logo compilandopodcast"></span>
<span class="title">Compilando Podcast</span>
<span class="mp3">
<a href="https://compilando.audio/wp-content/uploads/2017/04/CompilandoPodcast2.mp3">Podcast 2 – Especial Servidores Privados</a>
</span>
</span>
</li>
<li>
<span id="item-33">
<span class="logo compilandopodcast"></span>
<span class="title">Compilando Podcast</span>
<span class="mp3">
<a href="https://compilando.audio/wp-content/uploads/2017/04/podcast_1.mp3">Podcast 1- Ian Murdock, Debian y el proyecto QSL</a>
</span>
</span>
</li>
<li>
<span id="item-34">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/virtualizacion-ugeek-mosqueteroweb-face-to-face_mf_17898640_feed_1.mp3">Virtualizacion. uGeek y Mosqueteroweb. Face to Face.</a>
</span>
</span>
</li>
<li>
<span id="item-35">
<span class="logo compilandopodcast"></span>
<span class="title">Compilando Podcast</span>
<span class="mp3">
<a href="https://archive.org/download/PODCAST0_201704/PODCAST_0.mp3">Podcast 0 – Edición de presentación. Stallman y el síndrome Mi Pueblex.</a>
</span>
</span>
</li>
<li>
<span id="item-36">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601506.us.archive.org/26/items/38CrossoverConMosqueteroWeb/%23%2038%20Crossover%20con%20MosqueteroWeb.mp3">038. Crossover con MosqueteroWeb. Masterclass de FreeNas, Docker y virtualización mediante Proxmox y Esxi.</a>
</span>
</span>
</li>
<li>
<span id="item-37">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/112-llamadas-voz-telegram-cada-dia_mf_17886542_feed_1.mp3">#112 Llamadas de voz en Telegram, cada día mejor</a>
</span>
</span>
</li>
<li>
<span id="item-38">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801503.us.archive.org/18/items/037LlamadasDeTelegram/%23037%20Llamadas%20de%20Telegram.mp3">037. Llamadas de Telegram ya estan aquí. Y 3 bots que os encantaran</a>
</span>
</span>
</li>
<li>
<span id="item-39">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601509.us.archive.org/25/items/036PodcastConFrank/%23036%20podcast%20con%20Frank.mp3">036. Podcast con Frank de Batería2x100, Servidores Linux y NAS, lo mismo pero  diferente</a>
</span>
</span>
</li>
<li>
<span id="item-40">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-21-lets-encrypt.mp3">Podcast #21: Let’s Encrypt</a>
</span>
</span>
</li>
<li>
<span id="item-41">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/21-gnu-linux-universidad_mf_17834272_feed_1.mp3">#21 GNU/Linux en la Universidad</a>
</span>
</span>
</li>
<li>
<span id="item-42">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-20-como-ganar-dinero-con-el-podcast.mp3">Podcast #20: Cómo ganar dinero con el podcast</a>
</span>
</span>
</li>
<li>
<span id="item-43">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/freenas-servidor-hp-gen8-contenedores-y-maquinas_mf_17803755_feed_1.mp3">FreeNAS , Servidor HP Gen8, Contenedores Y Máquinas Virtuales</a>
</span>
</span>
</li>
<li>
<span id="item-44">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601501.us.archive.org/10/items/035MiG8/%23035%20Mi%20G8.mp3">035. Mi HP ProLiant MicroServer Gen8</a>
</span>
</span>
</li>
<li>
<span id="item-45">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801500.us.archive.org/9/items/034BotDeTelegramSustitutoAShazam/%23034%20Bot%20de%20Telegram%20sustituto%20a%20Shazam.mp3">034. Bots de Telegram Sustitutos a Shazam y busqueda de articulos dentro del bot de Pocket</a>
</span>
</span>
</li>
<li>
<span id="item-46">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/chromebooks-raspi-xiaomi-note-4-ultraportatil-jumper_mf_17764920_feed_1.mp3">Chromebooks, raspi, Xiaomi Note 4 y ultraportátil Jumper</a>
</span>
</span>
</li>
<li>
<span id="item-47">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-19-openvpn.mp3">Podcast #19: OpenVPN</a>
</span>
</span>
</li>
<li>
<span id="item-48">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601500.us.archive.org/4/items/033BotDePocketParaTelegram/%23033%20Bot%20de%20Pocket%20para%20Telegram.mp3">033. Bots en Telegram. Bot de Pocket</a>
</span>
</span>
</li>
<li>
<span id="item-49">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601606.us.archive.org/30/items/032MiscelaneaDeViernes/%23032%20Miscel%C3%A1nea%20de%20Viernes.mp3">032. Miscelánea de Viernes</a>
</span>
</span>
</li>
<li>
<span id="item-50">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601606.us.archive.org/14/items/031Keepass.ComoGestionoMisContrasenas/%23031%20Keepass.%20Como%20gestiono%20mis%20contrase%C3%B1as.mp3">031. Keepass, como gestiono mis contraseñas</a>
</span>
</span>
</li>
<li>
<span id="item-51">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601609.us.archive.org/0/items/030Mumble/%23030%20Mumble.mp3">030. Mumble, VoIP de Software Libre. Nextcloud, Wallabag y kdenlive</a>
</span>
</span>
</li>
<li>
<span id="item-52">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/111-problemas-focusrite-scarlett-solo-y_mf_17626877_feed_1.mp3">#111 Problemas con la Focusrite Scarlett Solo y 2i2 en macOS Sierra</a>
</span>
</span>
</li>
<li>
<span id="item-53">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-18-herramientas-simples-y-utiles-para-un-adminsitrador-de-red.mp3">Podcast #18: Herramientas simples y útiles para un adminsitrador de red</a>
</span>
</span>
</li>
<li>
<span id="item-54">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601608.us.archive.org/28/items/029MiscelneaDeViernes/%23029%20Miscel%C3%A1nea%20de%20viernes.mp3">029. Miscelánea de Viernes.</a>
</span>
</span>
</li>
<li>
<span id="item-55">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601607.us.archive.org/17/items/ugeekpodcast_gmail_XMPP/XMPP.mp3">028. Instala un servidor de mensajeria tipo Whatsapp o Telegram y de Software Libre con XMPP/Jabber</a>
</span>
</span>
</li>
<li>
<span id="item-56">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/20-linux-connexion-david-montalva-lliurex_mf_17557164_feed_1.mp3">#20 Linux Connexion con David Montalva (Lliurex)</a>
</span>
</span>
</li>
<li>
<span id="item-57">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/110-armando-nuevo-pc-para-linux_mf_17538251_feed_1.mp3">#110 Armando un nuevo PC para Linux</a>
</span>
</span>
</li>
<li>
<span id="item-58">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601606.us.archive.org/3/items/027InstalaTuVpnEnUbuntuORaspberryPi/%23027%20instala%20tu%20vpn%20en%20Ubuntu%20o%20Raspberry%20Pi.mp3">027. Instala una VPN (OpenVpn) en Ubuntu o Raspberry Pi con PiVpn</a>
</span>
</span>
</li>
<li>
<span id="item-59">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-17-sistemas-de-monitorizacion-de-sistemas-y-red.mp3">Podcast #17: Sistemas de monitorización de sistemas y red</a>
</span>
</span>
</li>
<li>
<span id="item-60">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-16-directo-11-marzo-2017.mp3">Podcast #16: Directo 11 de Marzo 2017</a>
</span>
</span>
</li>
<li>
<span id="item-61">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601606.us.archive.org/25/items/026PodcastConFrankDeBatera2x100/%23026%20Podcast%20con%20Frank%20de%20Bater%C3%ADa2x100.mp3">026. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestras Fotos, actualidad y sorteo del libro del año</a>
</span>
</span>
</li>
<li>
<span id="item-62">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/transexualidad_mf_17427425_feed_1.mp3">Transexualidad</a>
</span>
</span>
</li>
<li>
<span id="item-63">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/flintos-raspberry-pi-vernee-thor_mf_17416576_feed_1.mp3">FlintOS, Raspberry PI y Vernee Thor</a>
</span>
</span>
</li>
<li>
<span id="item-64">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601600.us.archive.org/16/items/025MtodoMMsCompletoQueParaRecopilarNotasOrgMode/%23025%20M%C3%A9todo%20m%C3%A1s%20completo%20que%20para%20recopilar%20notas%2C%20org%20mode.mp3">025. Metodo mas completo para recopilar notas, org Mode</a>
</span>
</span>
</li>
<li>
<span id="item-65">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/109-mi-vuelta-a-antergos-linux-al-estilo_mf_17415345_feed_1.mp3">#109 Mi vuelta a Antergos Linux al estilo Atlético de Madrid</a>
</span>
</span>
</li>
<li>
<span id="item-66">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601605.us.archive.org/10/items/024ConectateRemotamenteATuRaspberryPiCondataplicity/%23024%20Conectate%20remotamente%20a%20tu%20Raspberry%20Pi%20con%20%22dataplicity%22%20.mp3">024. Conectate remotamente a tu Raspberry Pi con "dataplicity"</a>
</span>
</span>
</li>
<li>
<span id="item-67">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-15-mumble.mp3">Podcast #15: Mumble, tu mesa de reuniones virtual</a>
</span>
</span>
</li>
<li>
<span id="item-68">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/108-directo-asi-estan-cosas-marzo_mf_17354573_feed_1.mp3">#108 Directo - Así están las cosas (Marzo 2017)</a>
</span>
</span>
</li>
<li>
<span id="item-69">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801609.us.archive.org/20/items/EntrevistaADosDesarrolladoresDeSoftwareLibreDeIgalia/Entrevista%20a%20dos%20desarrolladores%20de%20Software%20Libre%20de%20Igalia.mp3">023. Entrevista a Chema y Juan, dos desarrolladores de Software Libre de Igalia.com en el #mwc17</a>
</span>
</span>
</li>
<li>
<span id="item-70">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601600.us.archive.org/33/items/EntrevistaConArturoSuarezDirectivoDelCloudDeCanonicalUbuntu/Entrevista%20con%20Arturo%20Suarez,%20Directivo%20del%20Cloud%20de%20Canonical%20Ubuntu.mp3">022. Entrevista con Arturo Suarez, DIrectivo del Cloud de Canonical Ubuntu</a>
</span>
</span>
</li>
<li>
<span id="item-71">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/19-gnu-linux-escuela_mf_17289281_feed_1.mp3">#19 GNU/Linux en la escuela</a>
</span>
</span>
</li>
<li>
<span id="item-72">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/amd-vs-intel-samsung-nokia-mwc-spotify-cloudflare_mf_17285109_feed_1.mp3">AMD vs Intel. Samsung. Nokia MWC Spotify Cloudflare Martingala</a>
</span>
</span>
</li>
<li>
<span id="item-73">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-14-radio-o-podcast.mp3">Podcast #14: Radio o Podcast, no elijas puedes tener las dos</a>
</span>
</span>
</li>
<li>
<span id="item-74">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801606.us.archive.org/21/items/021UbuntuEnMobileWorldCongress/%23021%20ubuntu%20en%20Mobile%20World%20Congress%20.mp3">021. Ubuntu en el Mobile World Congress</a>
</span>
</span>
</li>
<li>
<span id="item-75">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-13-ospf-multiarea.mp3">Podcast #13: OSPF Multiárea</a>
</span>
</span>
</li>
<li>
<span id="item-76">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601601.us.archive.org/7/items/20PodcastConFrankDeBatera2x100HablamosDeComoGestionamosNuestraNotas/%2320%20Podcast%20con%20Frank%20de%20Bater%c3%ada2x100%2c%20Hablamos%20de%20como%20gestionamos%20nuestra%20notas%20.mp3">020. Podcast con Frank de Batería2x100, Hablamos de como gestionamos nuestra notas y mucho mas...</a>
</span>
</span>
</li>
<li>
<span id="item-77">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/noticias-tecnologicas_mf_17193972_feed_1.mp3">Noticias Tecnológicas</a>
</span>
</span>
</li>
<li>
<span id="item-78">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601603.us.archive.org/6/items/019DokuwikiNuevaFormaDeTomarMisNotas/%23019%20Dokuwiki%2c%20nueva%20forma%20de%20tomar%20mis%20notas%20.mp3">019. Dokuwiki, nueva forma de tomar mis notas. Monta tu wiki con DokuWiki o MediaWiki.</a>
</span>
</span>
</li>
<li>
<span id="item-79">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601604.us.archive.org/24/items/018WallabagElPocketOInstapaper/%23018_Wallabag%2c_el_Pocket_o_Instapaper.mp3">018. Como montar Wallabag, el Pocket o Instapaper de software libre y lo mejor de todo, en tu servidor</a>
</span>
</span>
</li>
<li>
<span id="item-80">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-12-atencion-al-cliente-y-migrar-una-web.mp3">Podcast #12: Atención al cliente y migrar una web</a>
</span>
</span>
</li>
<li>
<span id="item-81">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801300.us.archive.org/34/items/017PodcastConFrankDeBateria2x100HablandoDePlexNextcloud.../%23017%20Podcast%20con%20Frank%20de%20Bateria2x100%2c%20hablando%20de%20Plex%2c%20Nextcloud....mp3">017. Podcast con Frank de Bateria2x100, hablando de Plex, Nextcloud...</a>
</span>
</span>
</li>
<li>
<span id="item-82">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801603.us.archive.org/24/items/016QueEsUnServidor/%23016%20Que%20es%20un%20servidor.mp3">016. Que es un Servidor (dudas oyentes), servidor web, ...</a>
</span>
</span>
</li>
<li>
<span id="item-83">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801603.us.archive.org/20/items/015AlmacenamientoTheNextcloud/%23015_almacenamiento_the_nextcloud.mp3">015. Como ampliar el almacenamiento de Nextcloud, combinar con nubes publicas y hacer copias de mis fotos.</a>
</span>
</span>
</li>
<li>
<span id="item-84">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/18-linux-connexion-bitacora-ciberseguridad_mf_17029145_feed_1.mp3">#18 Linux Connexion con Bitácora de Ciberseguridad</a>
</span>
</span>
</li>
<li>
<span id="item-85">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601602.us.archive.org/11/items/NotasEnNextcloud/Notas%20en%20nextcloud.mp3">014. Notas en Nextcloud y Markdown</a>
</span>
</span>
</li>
<li>
<span id="item-86">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801601.us.archive.org/21/items/013NewsYFreshRSS.GestorDeNoticiasRSS/%23013%20News%20y%20Fresh%20RSS.%20Gestor%20de%20Noticias%20RSS.mp3">013. News y FreshRSS. Gestor de Noticias RSS.</a>
</span>
</span>
</li>
<li>
<span id="item-87">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801604.us.archive.org/21/items/013FDroidAplicacionesDeSoftwareLibre/%23013%20F-Droid%20Aplicaciones%20de%20Software%20Libre.mp3">013. bis F-Droid Tienda Android de aplicaciones de Software Libre y Actualizar las Noticias en Nextcloud.</a>
</span>
</span>
</li>
<li>
<span id="item-88">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/107-no-soy-fanboy_mf_16980247_feed_1.mp3">#107 No soy un Fanboy</a>
</span>
</span>
</li>
<li>
<span id="item-89">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801601.us.archive.org/24/items/012CmoActualizarNextcloudY/%23012_c%c3%b3mo_actualizar_Nextcloud_y.mp3">012. Como actualizar Nextcloud y salir del modo de "mantenimiento"</a>
</span>
</span>
</li>
<li>
<span id="item-90">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/w10-no-va-bien-mac-vs-linux-directo_mf_16950998_feed_1.mp3">W10 NO va bien. Mac vs Linux. Directo con ChineseDroid+AndroyTecno</a>
</span>
</span>
</li>
<li>
<span id="item-91">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-11-ospf-en-un-area.mp3">Podcast #11: OSPF en un único área</a>
</span>
</span>
</li>
<li>
<span id="item-92">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801602.us.archive.org/16/items/011PodcastConFrankDeBateria2x100/%23011%20Podcast%20con%20Frank%20de%20Bateria2x100.mp3">011. Podcast con Frank de Bateria2x100, hablando un poco de todo...</a>
</span>
</span>
</li>
<li>
<span id="item-93">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/106-linux-no-es-dificil-somos-viejos_mf_16934360_feed_1.mp3">#106 Linux no es difícil, somos los viejos usuarios quienes lo hacemos así</a>
</span>
</span>
</li>
<li>
<span id="item-94">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601603.us.archive.org/9/items/010ElSistemaOperativoDeBolsillo/%23010%20El%20Sistema%20Operativo%20de%20bolsillo.mp3">010. CloudReady el Chromium OS de bolsillo</a>
</span>
</span>
</li>
<li>
<span id="item-95">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601602.us.archive.org/11/items/ComoCrearTuPodcastYTotalmenteGtatis/Como%20crear%20tu%20podcast%20y%20totalmente%20gtatis.mp3">009. Crea tu podcast en 3 simples pasos y totalmente gratis</a>
</span>
</span>
</li>
<li>
<span id="item-96">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801900.us.archive.org/13/items/008ComoGestionoMisNotas/%23008%20Como%20gestiono%20mis%20notas.mp3">008. Como gestiono mis Notas</a>
</span>
</span>
</li>
<li>
<span id="item-97">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/batiburrillo-androytecno_mf_16862300_feed_1.mp3">Batiburrillo con AndroyTecno</a>
</span>
</span>
</li>
<li>
<span id="item-98">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="hhttps://ia601902.us.archive.org/28/items/007LinuxEsUnaAlternativaReal/%23007%20Linux%20es%20una%20alternativa%20real.mp3">007. Linux es una alternativa real</a>
</span>
</span>
</li>
<li>
<span id="item-99">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601900.us.archive.org/18/items/ElTrelloDeSoftwareLibreWekan/El_Trello_de_software_libre_Wekan.mp3">006. El Trello de Software Libre Wekan y Kanboard para Raspberry Pi. El sistema Kanban en tu servidor.</a>
</span>
</span>
</li>
<li>
<span id="item-100">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/105-directo-asi-estan-cosas-febrero-2017_mf_16815748_feed_1.mp3">#105 #Directo Así están las cosas (Febrero 2017)</a>
</span>
</span>
</li>
<li>
<span id="item-101">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-10-dns-y-arp.mp3">Podcast #10: Cómo funciona el DNS</a>
</span>
</span>
</li>
<li>
<span id="item-102">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601603.us.archive.org/9/items/005PaperDeDropbox/%23005%20Paper%20de%20Dropbox.mp3">005. Paper de Dropbox</a>
</span>
</span>
</li>
<li>
<span id="item-103">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/17-linux-connexion-alexandre-filgueira_mf_16768269_feed_1.mp3">#17 Linux Connexion con Alexandre Filgueira</a>
</span>
</span>
</li>
<li>
<span id="item-104">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-9-streaming-con-icecat2-mp3.mp3">Podcast #9: Streaming con Icecast 2</a>
</span>
</span>
</li>
<li>
<span id="item-105">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601903.us.archive.org/19/items/004ServidorLinuxVsQNapSynology/%23004%20Servidor%20Linux%20Vs%20QNap-Synology.mp3">004. Servidor Linux Vs QNAP-Synology</a>
</span>
</span>
</li>
<li>
<span id="item-106">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia601903.us.archive.org/4/items/003Nextcloud/%23003%20Nextcloud.mp3">003. Nextcloud. Instalar tu Nube en menos de 2 minutos.</a>
</span>
</span>
</li>
<li>
<span id="item-107">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801904.us.archive.org/20/items/DeQueVaEstoDeUGeek/De%20que%20va%20esto%20de%20uGeek%3f.mp3">002. "De qué va esto de uGeek?"</a>
</span>
</span>
</li>
<li>
<span id="item-108">
<span class="logo ugeek"></span>
<span class="title">uGeek</span>
<span class="mp3">
<a href="https://ia801602.us.archive.org/21/items/HolaMundo_201701/Hola%20Mundo.mp3">001. Hola Mundo</a>
</span>
</span>
</li>
<li>
<span id="item-109">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-8-el-viaje-de-cargar-una-web.mp3">Podcast #8: El viaje de cargar una web</a>
</span>
</span>
</li>
<li>
<span id="item-110">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/104-probando-3-cacharros-amazon-adaptadores-wifi_mf_16547697_feed_1.mp3">#104 Probando 3 cacharros de Amazon: Adaptadores Wifi, Bluetooth y disco duro Sata</a>
</span>
</span>
</li>
<li>
<span id="item-111">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/16-antergos_mf_16451726_feed_1.mp3">#16 Antergos</a>
</span>
</span>
</li>
<li>
<span id="item-112">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-7-cableado.mp3">Podcast #7: Cableado en un Centro de Datos</a>
</span>
</span>
</li>
<li>
<span id="item-113">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/15-linux-connexion-jen0f0nte_mf_15880251_feed_1.mp3">#15 Linux Connexion con Jen0f0nte</a>
</span>
</span>
</li>
<li>
<span id="item-114">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/103-esto-se-va-a-descontrolar-sobre-tuxlibanes_mf_15817492_feed_1.mp3">#103 Esto se va a descontrolar: Sobre tuxlibanes, blogs linuxeros y sus comunidades</a>
</span>
</span>
</li>
<li>
<span id="item-115">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-6-almacenamiento.mp3">Podcast #6: Almacenamiento</a>
</span>
</span>
</li>
<li>
<span id="item-116">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/102-balance-linuxero-2016-deseos-para-2017_mf_15446331_feed_1.mp3">#102 Balance linuxero 2016 y deseos para 2017 por el Killall Radio Podcast Team</a>
</span>
</span>
</li>
<li>
<span id="item-117">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/14-especial-slimbook-katana_mf_15380402_feed_1.mp3">#14 Especial Slimbook Katana</a>
</span>
</span>
</li>
<li>
<span id="item-118">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-5-cloud-centros-de-datos.mp3">Podcast #5: Introducción al Cloud y servicios de Centros de Datos</a>
</span>
</span>
</li>
<li>
<span id="item-119">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/101-linux-uefi-gpt-mbr-los_mf_15114926_feed_1.mp3">#101 Linux en UEFI GPT MBR y los instaladores de las distribuciones</a>
</span>
</span>
</li>
<li>
<span id="item-120">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/13-ciberseguridad-basica-gnu-linux_mf_14880771_feed_1.mp3">#13 Ciberseguridad Básica en GNU/Linux</a>
</span>
</span>
</li>
<li>
<span id="item-121">
<span class="logo salmorejogeek"></span>
<span class="title">Salmorejo Geek</span>
<span class="mp3">
<a href="http://www.ivoox.com/100-engrasando-ubuntu-a-vueltas-la_mf_14836526_feed_1.mp3">#100 Engrasando con Ubuntu, a vueltas con la distro única</a>
</span>
</span>
</li>
<li>
<span id="item-122">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-4-ssl-spam-postventa-de-apple.mp3">Podcast #4: SSL, spam y postventa de Apple</a>
</span>
</span>
</li>
<li>
<span id="item-123">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/w10-2gb-moto-mods-no-raid_mf_14773966_feed_1.mp3">W10 +2GB Moto Mods, No Raid</a>
</span>
</span>
</li>
<li>
<span id="item-124">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-3-como-crear-un-podcast.mp3">Podcast #3: Cómo crear un podcast</a>
</span>
</span>
</li>
<li>
<span id="item-125">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/12-linux-connexion-alejandro-lopez-slimbook_mf_14164009_feed_1.mp3">#12 Linux Connexion con Alejandro López ( Slimbook )</a>
</span>
</span>
</li>
<li>
<span id="item-126">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-2-crud-en-rails-formularios-dinamicos.mp3">Podcast #2: Git, CRUD en Rails y Formularios dinámicos en HTML con JavaScript</a>
</span>
</span>
</li>
<li>
<span id="item-127">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/11-linux-connexion-gabriel-viso-pitando-net-podcast_mf_13759097_feed_1.mp3">#11 Linux Connexion con Gabriel Viso (Pitando.net). Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-128">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-1-presentacion-rails-lynda.mp3">Podcast #1: Presentación, Rails y Lynda.com</a>
</span>
</span>
</li>
<li>
<span id="item-129">
<span class="logo eduardocollado"></span>
<span class="title">Eduardo Collado</span>
<span class="mp3">
<a href="https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-0.mp3">Podcast #0: Presentación</a>
</span>
</span>
</li>
<li>
<span id="item-130">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/10-raspberry-pi-gnu-linux-podcast-linux_mf_13546779_feed_1.mp3">#10 Raspberry Pi y GNU/Linux. Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-131">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/linux-ha-vencido-cuidado-linux_mf_13467162_feed_1.mp3">Linux ha vencido! Cuidado con Linux!</a>
</span>
</span>
</li>
<li>
<span id="item-132">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/moviles-servidor-casero_mf_13366716_feed_1.mp3">Móviles y Servidor Casero</a>
</span>
</span>
</li>
<li>
<span id="item-133">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/09-especial-lenovo-thinkpad-x220_mf_13265714_feed_1.mp3">#09 Especial Lenovo ThinkPad X220</a>
</span>
</span>
</li>
<li>
<span id="item-134">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/08-sabores-a-montones_mf_13103580_feed_1.mp3">#08 Sabores a montones</a>
</span>
</span>
</li>
<li>
<span id="item-135">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/distribuciones-linux-recomendaciones_mf_13011221_feed_1.mp3">Distribuciones Linux. Recomendaciones</a>
</span>
</span>
</li>
<li>
<span id="item-136">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/07-linux-connexion-huezo-grupo-telegram_mf_12912418_feed_1.mp3">#07 Linux Connexion con Huezo (Grupo Telegram GNU-Linux)</a>
</span>
</span>
</li>
<li>
<span id="item-137">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/07-linux-connexion-huezo-grupo-telegram-gnu-linux_mf_13383404_feed_1.mp3">#07 Linux Connexion con Huezo (Grupo Telegram GNU/Linux) Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-138">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/verano-tecnologia_mf_12810335_feed_1.mp3">Verano y Tecnología.</a>
</span>
</span>
</li>
<li>
<span id="item-139">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/06-conlinuxsisepuede_mf_12737297_feed_1.mp3">#06 #ConLinuxSíSePuede</a>
</span>
</span>
</li>
<li>
<span id="item-140">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/06-conlinuxsisepuede-podcast-linux_mf_13383405_feed_1.mp3">#06 #ConLinuxSíSePuede. Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-141">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/05-linux-connexion-yoyo-fernandez_mf_12593330_feed_1.mp3">#05 Linux Connexion con Yoyo Fernández</a>
</span>
</span>
</li>
<li>
<span id="item-142">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/05-linux-connexion-yoyo-fernandez_mf_13383406_feed_1.mp3">#05 Linux Connexion con Yoyo Fernández</a>
</span>
</span>
</li>
<li>
<span id="item-143">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/04-amor-distro-madre_mf_12520959_feed_1.mp3">#04 Amor de (Distro) madre</a>
</span>
</span>
</li>
<li>
<span id="item-144">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/04-amor-distro-madre-podcast-linux_mf_13383407_feed_1.mp3">#04 Amor de Distro Madre. Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-145">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/03-y-no-estaba-muerto-no-no_mf_12374536_feed_1.mp3">#03 Y no estaba muerto, no no</a>
</span>
</span>
</li>
<li>
<span id="item-146">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/03-y-no-estaba-muerto-no-no-podcast_mf_13383408_feed_1.mp3">#03 Y no estaba muerto, no, no. Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-147">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/02-un-pinguino-mi-usb_mf_12218805_feed_1.mp3">#02 Un pingüino en mi USB</a>
</span>
</span>
</li>
<li>
<span id="item-148">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/02-un-pinguino-mi-usb-podcast-linux_mf_13383409_feed_1.mp3">#02 Un pingüino en mi USB Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-149">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/50gb-20euros-audio-mejorado-linea-vacaciones-vodafone-linux-mint-18_mf_12098132_feed_1.mp3">50GB-20€ audio Mejorado.Línea vacaciones Vodafone, Linux Mint 18, teclast x89</a>
</span>
</span>
</li>
<li>
<span id="item-150">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/01-antecedentes_mf_12085902_feed_1.mp3">#01 Antecedentes</a>
</span>
</span>
</li>
<li>
<span id="item-151">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/01-antecedentes-podcast-linux_mf_13383410_feed_1.mp3">#01 Antecedentes. Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-152">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/00-promo-podcast-linux_mf_12048502_feed_1.mp3">#00 Promo Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-153">
<span class="logo podcastlinux"></span>
<span class="title">Podcast Linux</span>
<span class="mp3">
<a href="http://www.ivoox.com/00-promo-podcast-linux_mf_13383411_feed_1.mp3">#00 Promo Podcast Linux</a>
</span>
</span>
</li>
<li>
<span id="item-154">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/teclast-x89-kindow-chromebook-otras-noticias_mf_11777780_feed_1.mp3">Teclast x89 kindow. Chromebook y otras noticias</a>
</span>
</span>
</li>
<li>
<span id="item-155">
<span class="logo mosqueteroweb"></span>
<span class="title">MosqueteroWeb</span>
<span class="mp3">
<a href="http://www.ivoox.com/tablet-portatil-2x1-boligrafos-digitales-editores-pdf_mf_11399575_feed_1.mp3">Tablet + portátil 2x1 Boligrafos digitales Editores pdf</a>
</span>
</span>
</li>
        </ul>
    </div>
</body>
</html>

## uGeek
* [051. Adiós Blogger, Hola GitHub!](http://www.ivoox.com/051-adios-blogger-hola-github_mf_18499905_feed_1.mp3)
* [050. Que ando haciendo, nuevas publicaciones y más...](http://www.ivoox.com/050-que-ando-haciendo-nuevas-publicaciones-mas_mf_18441571_feed_1.mp3)
* [049. Instalar Syncthing en Ubuntu (derivadas de Debian), Antergos o Raspberry Pi](http://www.ivoox.com/049-instalar-syncthing-ubuntu-derivadas-debian_mf_18412436_feed_1.mp3)
* [048. Encuentro de amiguetes](http://www.ivoox.com/048-encuentro-amiguetes_mf_18398457_feed_1.mp3)
* [047. Se quemó la SD. Comparación de consumos entre PC, NAS-Microserver, Raspberry Pi](http://www.ivoox.com/047-se-quemo-sd-comparacion-consumos_mf_18367055_feed_1.mp3)
* [#046 Sincronización de carpetas entre dispositivos. Syncthing, Resilio y Dukto](http://www.ivoox.com/046-sincronizacion-carpetas-entre-dispositivos-syncthing-resilio_mf_18260109_feed_1.mp3)
* [#045 Crossover con Salmorejo Geek, donde hablamos de Mastodon, Ubuntu, Telegram y mucho mas...](http://www.ivoox.com/045-crossover-salmorejo-geek-donde-hablamos-de_mf_18112496_feed_1.mp3)
* [#044 La web de Jekyll en GitHub, va tomando forma](http://www.ivoox.com/044-la-web-jekyll-github-va_mf_18089929_feed_1.mp3)
* [#043 Bot de Telegram IFTTT](http://www.ivoox.com/043-bot-telegram-ifttt_mf_18064086_feed_1.mp3)
* [#042 El Atareao visita el Crossover de la Semana](http://www.ivoox.com/042-el-atareao-visita-crossover-la_mf_18041885_feed_1.mp3)
* [#041 Ubuntu y el adios a Unity](http://www.ivoox.com/041-ubuntu-adios-a-unity_mf_18024079_feed_1.mp3)
* [#40 Antergos, Ocnews De Nextcloud Y Jekyll](http://www.ivoox.com/40-antergos-ocnews-de-nextcloud-y-jekyll_mf_17994348_feed_1.mp3)
* [#039 Aplicación Notes de Nextcloud y crea tus bots de Telegram](http://www.ivoox.com/039-aplicacion-notes-nextcloud-crea-tus_mf_17910601_feed_1.mp3)
* [#038 Crossover con MosqueteroWeb. Masterclass de FreeNas, Docker y virtualización mediante Proxmox y Esxi.](http://www.ivoox.com/038-crossover-mosqueteroweb-masterclass-freenas-docker_mf_17898131_feed_1.mp3)
* [#037 Llamadas de Telegram ya estan aquí. Y 3 bots que os encantaran](http://www.ivoox.com/037-llamadas-telegram-ya-estan-aqui-y_mf_17863659_feed_1.mp3)
* [#036 Podcast con Frank de Batería2x100, Servidores Linux y NAS, lo mismo pero diferente](http://www.ivoox.com/036-podcast-frank-bateria2x100-servidores-linux_mf_17854761_feed_1.mp3)
* [#035 Mi HP ProLiant MicroServer Gen8](http://www.ivoox.com/035-mi-hp-proliant-microserver-gen8_mf_17799850_feed_1.mp3)
* [#034 Bots de Telegram Sustitutos a Shazam y busqueda de articulos dentro del bot de Pocket](http://www.ivoox.com/034-bots-telegram-sustitutos-a-shazam-y_mf_17799401_feed_1.mp3)
* [#033 Bots en Telegram. Bot de Pocket](http://www.ivoox.com/033-bots-telegram-bot-pocket_mf_17748621_feed_1.mp3)
* [#032 Miscelánea de Viernes](http://www.ivoox.com/032-miscelanea-viernes_mf_17745347_feed_1.mp3)

## Podcast Linux
* [#23 La Terminal](http://tracking.feedpress.it/link/15712/5735440/PL-23-Terminal.mp3)
* [#22 Linux Connexion con la OSL de la Universidad de La Laguna](http://tracking.feedpress.it/link/15712/5661934/PL-22-OSL-ULL.mp3)
* [GNU/Linux en la Universidad](http://tracking.feedpress.it/link/15712/5584665/PL-21-Universidad.mp3)
* [#20 Linux Connexion con David Montalva (Lliurex)](http://tracking.feedpress.it/link/15712/5510036/20-Lliurex.mp3)
* [#19 GNU/Linux en la escuela](http://tracking.feedpress.it/link/15712/5435264/19-GNULinux-Escuela.mp3)
* [#18 Linux Connexion con Bitácora de Ciberseguridad](http://tracking.feedpress.it/link/15712/5318870/18-Bitacora-Ciberseguridad.mp3)
* [#17 Linux Connexion con Alexandre Filgueira](http://tracking.feedpress.it/link/15712/5243105/17_Alex_Felgueira.mp3)
* [#16 Antergos](http://tracking.feedpress.it/link/15712/5160156/16-Antergos.mp3)
* [#15 Linux Connexion con Jen0f0nte](http://tracking.feedpress.it/link/15712/5089850/Podcast_Connexion_Jenofonte.mp3)
* [#14 Especial Slimbook Katana](http://tracking.feedpress.it/link/15712/5027564/14_Slimbook_Katana.mp3)
* [#13 Ciberseguridad Básica en GNU/Linux](http://tracking.feedpress.it/link/15712/4952699/13Ciberseguridad_PodcastLinux.mp3)
* [#12 Linux Connexion con Alejandro López ( Slimbook )](http://tracking.feedpress.it/link/15712/4864815/12_PodcastLinux_AlejandroLopez_SlimbookOne.mp3)
* [#11 Linux Connexion con Gabriel Viso (Pitando.net). Podcast Linux](http://tracking.feedpress.it/link/15712/4794030/11_PodcastLinux_GabrielViso-1.mp3)
* [#10 Raspberry Pi y GNU/Linux. Podcast Linux](http://tracking.feedpress.it/link/15712/4789379/10_PodcastLinux_RaspberryPi.mp3)
* [#09 Especial Lenovo ThinkPad X220. Podcast Linux](http://tracking.feedpress.it/link/15712/4789111/09-Especial-Lenovo.mp3)
* [#08 Sabores a montones. Podcast Linux](http://tracking.feedpress.it/link/15712/4789112/Podcast-Linux-08-Sabores-a-montones.mp3)
* [#07 Linux Connexion con Huezo (Grupo Telegram GNU/Linux) Podcast Linux](http://tracking.feedpress.it/link/15712/4789113/Podcast-Linux-07-Linux-Connexion-con-Huezo-Grupo-Telegram-GNU-Linux.mp3)
* [#06 #ConLinuxSíSePuede. Podcast Linux](http://tracking.feedpress.it/link/15712/4789114/Podcast-Linux-06-ConLinuxSiSePuede.mp3)
* [#05 Linux Connexion con Yoyo Fernández](http://tracking.feedpress.it/link/15712/4789115/05-Linux-Connexion-con-Yoyo-Fernandez.mp3)
* [#04 Amor de Distro Madre. Podcast Linux](http://tracking.feedpress.it/link/15712/4789116/Podcast-Linux-04-Amor-de-Distro-madre.mp3)
* [#03 Y no estaba muerto, no, no. Podcast Linux](http://tracking.feedpress.it/link/15712/4789117/Podcast-Linux-03-Y-no-estaba-muerto-no-no.mp3)
* [#02 Un pingüino en mi USB Podcast Linux](http://tracking.feedpress.it/link/15712/4789118/Podcast-Linux-02-Un-pinguino-en-mi-USB.mp3)
* [#01 Antecedentes. Podcast Linux](http://tracking.feedpress.it/link/15712/4789119/Podcast-Linux-01-Antedecentes.mp3)
* [#00 Promo Podcast Linux](http://tracking.feedpress.it/link/15712/4789120/Podcast-Linux-00-Promo.mp3)

## Compilando Podcast
* [Podcast 4 – Jon “maddog” Hall , Open South Code y Linux y Tapas](http://compilando.audio/wp-content/uploads/2017/04/podcast4.mp3)
* [Podcast 3 – Entrevista con ” el atareao” y el nuevo rumbo de Ubuntu](https://compilando.audio/wp-content/uploads/2017/04/Podcast_3.mp3)
* [Podcast 2 – Especial Servidores Privados](https://compilando.audio/wp-content/uploads/2017/04/CompilandoPodcast2.mp3)
* [Podcast 1- Ian Murdock, Debian y el proyecto QSL](https://compilando.audio/wp-content/uploads/2017/04/podcast_1.mp3)
* [Podcast 0 – Edición de presentación. Stallman y el síndrome Mi Pueblex.](https://archive.org/download/PODCAST0_201704/PODCAST_0.mp3)

## Salmorejo Geek
* [#119 Geekeando con Érika Betancor](http://www.ivoox.com/119-geekeando-erika-betancor_mf_18422071_feed_1.mp3)
* [#118 Directo: Así están las cosas (Abril 2017)](http://www.ivoox.com/118-directo-asi-estan-cosas-abril-2017_mf_18412331_feed_1.mp3)
* [#117 Sin sombra en el helicóptero](http://www.ivoox.com/117-sin-sombra-helicoptero_mf_18309317_feed_1.mp3)
* [#116 Conociendo Deepin GNU Linux 15.4](http://www.ivoox.com/116-conociendo-deepin-gnu-linux-15-4_mf_18295101_feed_1.mp3)
* [#115 Crossover con uGeek Podcast: Mastodon, Ubuntu y comunidad Linux, Telegram y mucho más](http://www.ivoox.com/115-crossover-ugeek-podcast-mastodon-ubuntu-y_mf_18112915_feed_1.mp3)
* [#114 Ubuntu abandona Unity y la Convergencia ¿Y ahora qué?](http://www.ivoox.com/114-ubuntu-abandona-unity-convergencia-y_mf_18057325_feed_1.mp3)
* [#113 Offtopiqueando ando: Informática, Semana Santa y Chuck Norris](http://www.ivoox.com/113-offtopiqueando-ando-informatica-semana-santa-chuck_mf_17909300_feed_1.mp3)
* [#112 Llamadas de voz en Telegram, cada día mejor](http://www.ivoox.com/112-llamadas-voz-telegram-cada-dia_mf_17886542_feed_1.mp3)
* [#111 Problemas con la Focusrite Scarlett Solo y 2i2 en macOS Sierra](http://www.ivoox.com/111-problemas-focusrite-scarlett-solo-y_mf_17626877_feed_1.mp3)
* [#110 Armando un nuevo PC para Linux](http://www.ivoox.com/110-armando-nuevo-pc-para-linux_mf_17538251_feed_1.mp3)
* [#109 Mi vuelta a Antergos Linux al estilo Atlético de Madrid](http://www.ivoox.com/109-mi-vuelta-a-antergos-linux-al-estilo_mf_17415345_feed_1.mp3)
* [#108 Directo - Así están las cosas (Marzo 2017)](http://www.ivoox.com/108-directo-asi-estan-cosas-marzo_mf_17354573_feed_1.mp3)
* [#107 No soy un Fanboy](http://www.ivoox.com/107-no-soy-fanboy_mf_16980247_feed_1.mp3)
* [#106 Linux no es difícil, somos los viejos usuarios quienes lo hacemos así](http://www.ivoox.com/106-linux-no-es-dificil-somos-viejos_mf_16934360_feed_1.mp3)
* [#105 #Directo Así están las cosas (Febrero 2017)](http://www.ivoox.com/105-directo-asi-estan-cosas-febrero-2017_mf_16815748_feed_1.mp3)
* [#104 Probando 3 cacharros de Amazon: Adaptadores Wifi, Bluetooth y disco duro Sata](http://www.ivoox.com/104-probando-3-cacharros-amazon-adaptadores-wifi_mf_16547697_feed_1.mp3)
* [#103 Esto se va a descontrolar: Sobre tuxlibanes, blogs linuxeros y sus comunidades](http://www.ivoox.com/103-esto-se-va-a-descontrolar-sobre-tuxlibanes_mf_15817492_feed_1.mp3)
* [#102 Balance linuxero 2016 y deseos para 2017 por el Killall Radio Podcast Team](http://www.ivoox.com/102-balance-linuxero-2016-deseos-para-2017_mf_15446331_feed_1.mp3)
* [#101 Linux en UEFI GPT MBR y los instaladores de las distribuciones](http://www.ivoox.com/101-linux-uefi-gpt-mbr-los_mf_15114926_feed_1.mp3)
* [#100 Engrasando con Ubuntu, a vueltas con la distro única](http://www.ivoox.com/100-engrasando-ubuntu-a-vueltas-la_mf_14836526_feed_1.mp3)

## MosqueteroWeb
* [Twitter, ¿sabemos usarlo? Android Audio y Pocket Casts](https://www.ivoox.com/twitter-sabemos-usarlo-android-audio-pocket-casts_mf_18349090_feed_1.mp3)
* [Seguridad por Hardware en tu Servidor casero](https://www.ivoox.com/seguridad-hardware-tu-servidor-casero_mf_18128440_feed_1.mp3)
* [¿Qué pasa con Ubuntu? Hablando de Linux con El Atareao y con uGeek](https://www.ivoox.com/que-pasa-ubuntu-hablando-linux-con_mf_18041732_feed_1.mp3)
* [Virtualizacion. uGeek y Mosqueteroweb. Face to Face.](https://www.ivoox.com/virtualizacion-ugeek-mosqueteroweb-face-to-face_mf_17898640_feed_1.mp3)
* [FreeNAS , Servidor HP Gen8, Contenedores Y Máquinas Virtuales](https://www.ivoox.com/freenas-servidor-hp-gen8-contenedores-y-maquinas_mf_17803755_feed_1.mp3)
* [Chromebooks, raspi, Xiaomi Note 4 y ultraportátil Jumper](https://www.ivoox.com/chromebooks-raspi-xiaomi-note-4-ultraportatil-jumper_mf_17764920_feed_1.mp3)
* [Transexualidad](https://www.ivoox.com/transexualidad_mf_17427425_feed_1.mp3)
* [FlintOS, Raspberry PI y Vernee Thor](https://www.ivoox.com/flintos-raspberry-pi-vernee-thor_mf_17416576_feed_1.mp3)
* [AMD vs Intel. Samsung. Nokia MWC Spotify Cloudflare Martingala](https://www.ivoox.com/amd-vs-intel-samsung-nokia-mwc-spotify-cloudflare_mf_17285109_feed_1.mp3)
* [Noticias Tecnológicas](https://www.ivoox.com/noticias-tecnologicas_mf_17193972_feed_1.mp3)
* [W10 NO va bien. Mac vs Linux. Directo con ChineseDroid+AndroyTecno](https://www.ivoox.com/w10-no-va-bien-mac-vs-linux-directo_mf_16950998_feed_1.mp3)
* [Batiburrillo con AndroyTecno](https://www.ivoox.com/batiburrillo-androytecno_mf_16862300_feed_1.mp3)
* [W10 +2GB Moto Mods, No Raid](https://www.ivoox.com/w10-2gb-moto-mods-no-raid_mf_14773966_feed_1.mp3)
* [Linux ha vencido! Cuidado con Linux!](https://www.ivoox.com/linux-ha-vencido-cuidado-linux_mf_13467162_feed_1.mp3)
* [Móviles y Servidor Casero](https://www.ivoox.com/moviles-servidor-casero_mf_13366716_feed_1.mp3)
* [Distribuciones Linux. Recomendaciones](https://www.ivoox.com/distribuciones-linux-recomendaciones_mf_13011221_feed_1.mp3)
* [Verano y Tecnología.](https://www.ivoox.com/verano-tecnologia_mf_12810335_feed_1.mp3)
* [50GB-20€ audio Mejorado.Línea vacaciones Vodafone, Linux Mint 18, teclast x89](https://www.ivoox.com/50gb-20euros-audio-mejorado-linea-vacaciones-vodafone-linux-mint-18_mf_12098132_feed_1.mp3)
* [Teclast x89 kindow. Chromebook y otras noticias](https://www.ivoox.com/teclast-x89-kindow-chromebook-otras-noticias_mf_11777780_feed_1.mp3)
* [Tablet + portátil 2x1 Boligrafos digitales Editores pdf](https://www.ivoox.com/tablet-portatil-2x1-boligrafos-digitales-editores-pdf_mf_11399575_feed_1.mp3)

## Eduardo Collado
* [Podcast #26: Odoo y transformación digital](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/05/podcast-26-odoo-y-transformacion.mp3)
* [Podcast #25: Introducción a Docker](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-25-introduccion-a-docker.mp3)
* [Podcast #24: Sobre Vlans](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-24-sobre-vlans.mp3)
* [Podcast #23: Calcular máscaras de red](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-23-calcular-mascaras-de-red.mp3)
* [Podcast #22: NAT en GNU/Linux](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/04/podcast-22-iptables-en-gnu-linux.mp3)
* [Podcast #21: Let’s Encrypt](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-21-lets-encrypt.mp3)
* [Podcast #20: Cómo ganar dinero con el podcast](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-20-como-ganar-dinero-con-el-podcast.mp3)
* [Podcast #19: OpenVPN](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-19-openvpn.mp3)
* [Podcast #18: Herramientas simples y útiles para un adminsitrador de red](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-18-herramientas-simples-y-utiles-para-un-adminsitrador-de-red.mp3)
* [Podcast #17: Sistemas de monitorización de sistemas y red](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-17-sistemas-de-monitorizacion-de-sistemas-y-red.mp3)
* [Podcast #16: Directo 11 de Marzo 2017](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-16-directo-11-marzo-2017.mp3)
* [Podcast #15: Mumble, tu mesa de reuniones virtual](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/03/podcast-15-mumble.mp3)
* [Podcast #14: Radio o Podcast, no elijas puedes tener las dos](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-14-radio-o-podcast.mp3)
* [Podcast #13: OSPF Multiárea](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-13-ospf-multiarea.mp3)
* [Podcast #12: Atención al cliente y migrar una web](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-12-atencion-al-cliente-y-migrar-una-web.mp3)
* [Podcast #11: OSPF en un único área](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-11-ospf-en-un-area.mp3)
* [Podcast #10: Cómo funciona el DNS](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/02/podcast-10-dns-y-arp.mp3)
* [Podcast #9: Streaming con Icecast 2](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-9-streaming-con-icecat2-mp3.mp3)
* [Podcast #8: El viaje de cargar una web](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-8-el-viaje-de-cargar-una-web.mp3)
* [Podcast #7: Cableado en un Centro de Datos](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2017/01/podcast-7-cableado.mp3)
* [Podcast #6: Almacenamiento](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-6-almacenamiento.mp3)
* [Podcast #5: Introducción al Cloud y servicios de Centros de Datos](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-5-cloud-centros-de-datos.mp3)
* [Podcast #4: SSL, spam y postventa de Apple](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-4-ssl-spam-postventa-de-apple.mp3)
* [Podcast #3: Cómo crear un podcast](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-3-como-crear-un-podcast.mp3)
* [Podcast #2: Git, CRUD en Rails y Formularios dinámicos en HTML con JavaScript](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-2-crud-en-rails-formularios-dinamicos.mp3)
* [Podcast #1: Presentación, Rails y Lynda.com](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-1-presentacion-rails-lynda.mp3)
* [Podcast #0: Presentación](https://media.blubrry.com/eduardocollado/www.eduardocollado.com/wp-content/uploads/2016/12/podcast-0.mp3)
