equalheight = function(container){

var currentTallest = 0,
     currentRowStart = 0,
     rowDivs = new Array(),
     $el,
	 detailBlockHeight=0,
     topPosition = 0;
	 
$(container).each(function() {
   $el = $(this);
   $($el).height('auto')
   topPostion = $el.position().top;
 
   if (currentRowStart != topPostion) {
     for (currentDiv = 0 ; currentDiv < rowDivs.length ; currentDiv++) {
       rowDivs[currentDiv].height(currentTallest);
     }
     rowDivs.length = 0; // empty the array
     currentRowStart = topPostion;
     currentTallest = $el.height();
     rowDivs.push($el);
   } else {
     rowDivs.push($el);
     currentTallest = (currentTallest < $el.height()) ? ($el.height()) : (currentTallest);
  }
  
   for (currentDiv = 0 ; currentDiv < rowDivs.length ; currentDiv++) {
     rowDivs[currentDiv].height(currentTallest);
	if(detailBlockHeight<currentTallest)
	{
	detailBlockHeight=detailBlockHeight+currentTallest;
	}
	
   }
   
});

/*if($(window).width()<1024)
{
$(".detail_block.carousel").height(detailBlockHeight);
}*/
}


equalheightfourCarousel = function(container){
 
var currentTallest = 0,
     currentRowStart = 0,
     rowDivs = new Array(),
     $el,
	 detailBlockHeight=0,
     topPosition = 0;
var heightVal=0;

$(container).each(function() {
heightVal=$('.corousal-header.spacer_s_all').height()+$('.corousal-body.spacer_s_all').height()+$('.block_inner').height();
   $el = $(this);
   $($el).height('auto')
   topPostion = $el.position().top;
 
   if (currentRowStart != topPostion) {
     for (currentDiv = 0 ; currentDiv < rowDivs.length ; currentDiv++) {
       rowDivs[currentDiv].height(currentTallest);
     }
     rowDivs.length = 0; // empty the array
     currentRowStart = topPostion;
     currentTallest = $el.height();
     rowDivs.push($el);
   } else {
     rowDivs.push($el);
     currentTallest = (currentTallest < $el.height()) ? ($el.height()) : (currentTallest);
  }
  
   for (currentDiv = 0 ; currentDiv < rowDivs.length ; currentDiv++) {
     rowDivs[currentDiv].height(currentTallest);
	if(detailBlockHeight<currentTallest)
	{
	detailBlockHeight=detailBlockHeight+currentTallest;
	}
	
   }
});

if($(window).width()<1024)
{
$(".detail_block.carousel").height(detailBlockHeight);
}
}
