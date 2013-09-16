expand-collapse-localstore
==========================

function toggleHeight(id, link) {
  var e = document.getElementById(id);
	var height = localStorage.getItem(id);

    if(e.style.maxHeight == '450px' || e.style.maxHeight == 'inherit') {
        e.style.maxHeight = '0px'; 
		link.innerHTML = '<p>&#x2B;</p> '+ id;
		localStorage.setItem(id,"closed");
    }
	else {
        e.style.maxHeight = '450px';
		link.innerHTML = '<p>&#x2212;</p> ' + id;
		localStorage.setItem(id, "open");
    }
}

function load() {
	
	var setting
	var e
	var link
	for (x in localStorage){
		setting = localStorage.getItem(x);
		e = document.getElementById(x);
		link = document.getElementById('forumlink'+x);
		
		if(setting == 'open') {
			e.style.maxHeight = '450px';
			link.innerHTML = '<p>&#x2212;</p> ' + x;
		}
		else {
			e.style.maxHeight = '0px';
			link.innerHTML = '<p>&#x2B;</p> '+ x;
		}	
	}
}
