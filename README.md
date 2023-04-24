# dsa
class Node:
  def __init__(self,value):
    self.value=value
    self.next=None
class Linkedlist:
  def __init__(self):
    self.head=None
  def  addvalue(self,value):
    new_node=Node(value)
    if self.head is None:
      self.head=new_node
    else:
      current=self.head
      while current.next is not None:
        current=current.next
      current.next=new_node
  def duplicate_unsorted(self):
    if self.head is None:
      return self.head
    seen=set()
    current=self.head
    seen.add(current.value)
    while current.next is not None:
      if current.next.value  in seen:
        current.next=current.next.next
      else:
        seen.add(current.next.value)
        current=current.next
    return self.head
  def duplicate_sorted(self):
    if self.head is None:
      return self.head
    current=self.head
    while current.next is not None:
      if current.value==current.next.value:
        current.next=current.next.next
      else:
        current=current.next
    return self.head
  def delete(self,nodevalue):
    if self.head is None:
      return
    if self.head.value==nodevalue:
      self.head=self.head.next
      return
    current=self.head
    while  current.next is not None:
      if current.next.value==nodevalue:
        current.next=current.next.next
      else:
        current=current.next
    
  def print(self):
    if self.head is None:
      print("no linked list exist")
    current=self.head
    while current:
      print(current.value,end="\n")
      current=current.next
    print()
linkedlist=Linkedlist()
linkedlist.addvalue(1)
linkedlist.addvalue(7)
linkedlist.addvalue(4)
linkedlist.addvalue(2)
linkedlist.addvalue(1)
linkedlist.print()
linkedlist.duplicate_unsorted()
linkedlist.print()
linkedlist.delete(4)
linkedlist.print()
   
