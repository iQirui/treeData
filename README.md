# treeData
Array.prototype.toTreeData=function(id,pid){
	if(!id || !pid){
		return null;
	}
	var id2Vo={};
	for(var i=0;i<this.length;i++){
		if(list[i][id]==null){
			return null;
		}
		id2Vo[list[i][id]]=list[i];
	}
	var currentPid;
	for(var i=0;i<list.length;i++){
		currentPid=list[i][pid];
		if(id2Vo[currentPid]){
			if(id2Vo[currentPid].children){
				id2Vo[currentPid].children.push(list[i]);
			}else{
				id2Vo[currentPid].children=[list[i]];
			}
			list.splice(i,1);
			i--;
		}
	}
	return id2Vo;
}
