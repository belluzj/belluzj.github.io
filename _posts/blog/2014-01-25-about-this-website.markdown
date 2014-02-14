---
layout: post
title:  "About this website"
categories: blog
---

### Licenses

Stylesheets and HTML layouts are based on the default ones from the
[Jekyll][jekyll] project, and are published under the MIT License.

License files to be downloaded [here][charter-ofl], [there][smcp-ofl],
[hither][league-ofl] & [yon][my-ofl].
{:.margin.note}

As for fonts, body text uses Charter, a free design by Bitstream, with [small
caps][smcp][^smallcaps] extracted from [Charis SIL][silint], another free font
based on Charter, by the SIL group. Titles are set in [League Gothic][league],
a free typeface brought to you by The League of Movable Type. And finally,
fixed-width text uses my own [Fantasque Sans Mono][fantasque].

[^smallcaps]:
    Having read in Butterick's book (and agreed) that fake small caps where
    <q>inferior counterfeits</q>, and Charter lacking real small caps (at least
    in the free version), I looked for a not-too-costly solution. There came
    the Charis SIL font, which in addition to its wide script support provided
    small caps through an Opentype feature. I used [FontSquirrel's webfont
    generator](http://www.fontsquirrel.com/tools/webfont-generator) to subset
    it and activate by default the `smcp` feature. Finally I used FontForge to
    rename it and make its vertical metrics match those of Charter.

I reserve all rights over the other contents of this website. In terms of Git
repository, that includes the first level `.markdown` files, everything under
the `_posts` directory, and everything I own in the `public` repository. Other
stuff inside `public` is copyright by their respective owners.



### About the design

Most of design choices have been inspired by the reading of [Butterick's
Practical Typography][typo-book]. I also use color codes from the
[Solarized][solarized] scheme, even though I guess I do not use them as
intended. Here are some examples of various HTML elements.

---------------

#### Tech items

You most certainly heartily desire to know every little detail about the technological
tools I use everyday. Let me satisfy your curiosity. 

I also have a Wacom Pen&Touch tablet, but I do not use it very often.
{:.margin.note}

<dl>
<dt>Laptop</dt>
<dd>I use a Lenovo Yoga 13, which is really good.</dd>
<dt>Smartphone</dt>
<dd>My phone is all but smart. It calls people. That's about it.</dd>
</dl>


#### Two Inspirational Quotes That Will Blow Your Mind (and some code)

> Any fool can write code that a computer can understand. Good programmers
> write code that humans can understand. --- Martin Fowler

I may not always achieve that goal, but at least I try. 

> Try not. Do or do not. There is no try. --- Yoda

Anyway, let's have a look at this marvelously entertaining snippet[^robair] of
high quality Python code:

{% highlight python %}
def send_bytes(self, *bytes_to_send):
    '''Sends the given bytes, preceded by a synchronisation.'''
    self.ser.write(Commands.SYNC);
    for b in bytes_to_send:
        self.ser.write(b)

def set_mode(self, mode):
    '''set the mode of the MD49'''
    self.send_bytes(Commands.SET_MODE, mode)

def stop_wheels(self):
    '''stop both motors'''
    self.set_mode(Modes.UNSIGNED_SEPARATE_SPEEDS)
    self.send_bytes(Commands.SET_SPEED_1_OR_BOTH, Speeds.NONE)
    self.send_bytes(Commands.SET_SPEED_2_OR_TURN, Speeds.NONE)
{% endhighlight %}

#### Tea and other edibles

> Tea: gentlemen's coffee.\\
> --- some tee-shirt
{:.margin}

I also take lifestyle advice from clothing items.
{:.margin.note.after}

I like tea. Where do I get it? Here is very insightful comparison of my two
favorite tea shops.  Of course, they both serve great tea.

Name           | Where    | Why it's good
---------------|----------|----------------------------------
Jardin du Thé  | Grenoble | Friendly staff and good pastries.
Mariage Frères | Paris    | Classy French touch.

Now, what about a list of my favourite foods?

* Cheese
   1. Mozzarella
   2. Comté
   3. Langres
* Fruit
   * Dry
      1. Raisin
      2. Apple
   * Fresh
      * *Any will do*

#### Meta-posting

Now this is about how I write my posts, and especially posts such as this very
[About this website](#) post that you are reading. Here is the Markdown needed
to get this paragraph and the code block below.

    #### Meta-posting
    
    Now this is about how I write my posts, and especially posts such as this very
    [About this website](#) post that you are reading. Here is the Markdown needed
    to get this paragraph and the code block below.
    
        #### Meta-posting
        
        Now this is about how I write my posts, and especially posts such as this very
        [About this website](#) post that you are reading. Here is the Markdown needed
        to get this paragraph and the code block below.
        
            #### Someone call the Doctor
            
            Some big loop is about to rip apart the fabric of space and time.    
        {:.fullwidth}
    {:.fullwidth}
{:.fullwidth}

Since this code is a bit large, I decided that it should go full-width. That
explains the `{:.fullwidth}` class. I do the same when I want stuff in the
margin. For example

Deep margin thoughts.
{:.margin}

    Deep margin thoughts.
    {:.margin}

gives the margin stuff on the left.

When I was a child, I used to do a lot of the things that children usually do,
except when I did something unusual, which may have happened, or not.
{:.margin.note}

When I want to tell a whole story in the margin, I make it smaller so it does
not spread its insignificance over multiple pages. It is then sufficient to add
the `.note` class, such as in

    When I was a child, I used to do a lot of the things
    that children usually do, except when I did something
    unusual, which may have happened, or not.
    {:.margin.note}



[fantasque]: {% post_url projects/2013-11-18-fantasquesansmono-font %}
[league]: http://www.theleagueofmoveabletype.com/league-gothic
[silint]: http://scripts.sil.org/cms/scripts/page.php?item_id=CharisSIL_Technical
[smcp]: https://github.com/belluzj/charterish-small-caps
[my-ofl]: /fonts/fantasquesansmono_LICENSE.txt
[league-ofl]: /fonts/leaguegothic_LICENSE.txt
[charter-ofl]: /fonts/charter_LICENSE.txt
[smcp-ofl]: /fonts/charterishsmallcaps_LICENSE.txt
[jekyll]: http://www.jekyllrb.com/
[typo-book]: http://www.practicaltypography.com/
[solarized]: http://www.ethanschoonover.com/solarized

[^robair]:
    The whole code is available in the [GitHub
    repository](https://github.com/belluzj/RobAir) of the [RobAir
    project]({% post_url projects/2013-06-14-robair %}).
