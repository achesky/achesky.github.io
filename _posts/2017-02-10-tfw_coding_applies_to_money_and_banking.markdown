---
layout: post
title:  "TFW Coding Applies to Money & Banking"
date:   2017-02-10 14:54:44 -0500
---

Before getting into this lab, I want to detail for a moment my experience on Learn.co so far (partly for posterity, partly because it's been a month). My coding path has been a bit confusing at times: I began with the intro courses to the FlatIron Full Stack Web Development Program which took me through Intro to Programming, some de-bugging, a lot of basics, and then an intro to Object Orientation. However, after completing only those intro portions and reviewing some basics of GitHub, I went to HTML & CSS. 

Before starting this program, I've built websites for internships (www.lizzysallnatural.com) using WordPress. I was in charge of creating another website over this past winter break from school and realized that the reason I was able to create that was due to WordPress PlugIns that an overhead team of IT had already input for me - truly I was lost in website creation without those handy-dandy plug-ins. For that reason, the HTML & CSS Course was incredibly rewarding for me. 

Now, every time I look at a website on laptop (and I constantly have more than one Chrome window open at a time, whether it's using Learn.co & the Learn IDE platform or doing homework, I notice every time the browser layout changes due to the change in the pixel size of my Chrome window. Then, of course, I have to inspect the page and see what pixels they set and see if that's the pixel width that I would have set. I also look at a lot of different newspaper websites every week and I've realized how generic those websites are - probably because they're owned by the same parent company - and I understand that they all derive from the same Bootstrap Package. 

Learning Ruby so far after the HTML & CSS hasn't given me the same 'aha' moments as HTML & CSS did every time I open up a web page, but it's given me some 'whoa' moments with the references to the music app domain models in the labs and lessons. I haven't quite reached the Final Projects section (somehow I forgot that homework assignments for school take time too) and this blog post is due in two days, so I figured I'd get this out of the way before I head into those which will probably take up a lot of my bandwidth for a bit. So for this blog post, I'm just going to get into the prompt of explaining how I use Object Models instead of explaining my thought process behind my final project for Ruby. 

My favorite lab in the Object-Oriented Ruby so far has been the oo-banking-v-000 lab, since I'm an Economics major and currently taking a Money & Banking class and we've been discussing different assets like checking accounts, so I'm going to detail that one. 

Building classes that interact with one another intimidated me a bit at first, because the concept of classes is a bit abstract to me to begin with. This lab instructed me to build two classes: `class BankAccount` and `class Transfer`. The `class BankAccount`needed various methods **#deposit** money, **#display_balance**, make sure the account was **#valid?**, and **#close_account**. To do this I created the variables `@name` `@balance` and `@status`, with the `@name` defined as `attr_reader :name` so that it could not be changed (this would cause lots of problems in the banking system if we could change our account names willy-nilly. Every account was **#initialize** with a name, a deposit of $1000, and `@status = "open"`. 

Then, I needed to build out the `class Transfer`, so that clients can transfer money between accounts or to one another (I Venmo my friends constantly and in my mind I was thinking whoa, I could probably extrapolate on this to re-create the Venmo app now). In this class, I needed to be able to define the `@sender`, `@receiver`, `@amount` of the transfer, and `@status` of the transfer (different from the account `@status`). 

What I like about Object-Oriented Ruby and these sorts of labs is it requires you to think about the different steps that are taken in the real-world occurrence we are trying to model. What happens first when we transfer money? The bank checks to make sure we have enough money in our account and that the account exists (is open, not closed): 

```
  def valid?
    if @sender.valid? == true && @receiver.valid? == true && @sender.balance > @amount
      true
    else
      false
    end
  end
```

The bank can check this by performing the **#valid?** method in the `class BankAccount` on the sender's and receiver's accounts, but also it needs to make sure that the sender has enough money to make the transfer. Once the bank ascertains that the transfer is possible, what does the bank do? It executes the transfer: 

```
def execute_transaction
    if valid? == true && @status == "pending"
      @sender.balance = @sender.balance - @amount
      @receiver.balance = @receiver.balance + @amount
      @status = "complete"
    else
      reject_transfer
    end
  end
```

To execute, the bank has to confirm that both accounts are valid and that the transaction hasn't gone through yet (`@status == "pending"`). If so, then the sender's balance decreases by the amount of the transfer, the receiver's balance increases by the amount of the transfer, and the status is changed to complete. If not, then the bank must reject the transfer request: 

```
  def reject_transfer
    @status = "rejected"
    "Transaction rejected. Please check your account balance."
  end
```

In this lab, I also included a method to reverse the transfer, if needed by the bank's clients:

```
  def reverse_transfer
    if @status == "complete"
      @sender.balance = @sender.balance + amount
      @receiver.balance = @receiver.balance - amount
      @status = "reversed"
    end
  end
```

You can also view this lab in my GitHub [here](https://github.com/achesky/oo-banking-v-000). 
