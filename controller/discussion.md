## Discussion controller

### GET searchClassDiscussions:  
Get discussions by class and publication ID

1.  get by prefix (‘discussion’)  
  1.  get from userRW  
  1.  get from course DB (online call)  
  1. get current user  //DB.userId()  
  1. concat and filter (uniq)  
1. get discussion activity  
  1. get activity for course  
  1. get discussion value  


![searchClassDiscussions](img/Discussion_GET_searchClassDiscussions.png)
![Discussion.getByPrefix](img/Discussion.getByPrefix.png)
![Discussion.getDiscussionActivity](img/Discussion.getDiscussionActivity.png)
