# FAQs

**What does the "|" symbol mean in the result window?**

This means "or". (And the symbol is pronounced "pipe".)

**What about snippets in my topics?**

They're fine: The plugin checks all snippets, too. However, it will miss some structural elements. For example, the plugin will flag a missing heading or a missing concept tag if these elements are not in the topic, but in the snippet. You can easily detect these false positives in the result window and ignore them.

**What about conditions in my topic?**

They're fine: When you verify a topic that contains conditions, some results about topic structure can be false positives because the plugin currently doesn't distinguish between different conditions.

**What about Tracked Changes in my topic?**

Proceed with care: Before verifying a topic, ensure your topic does not contain tracked changes. Nothing bad happens, but you will not get meaningful results for the parts in the topic code where tracked changes are present.

**How can I exclude elements based on the applied condition?**
To for example ignore paragraphs with a condition, use  this context: ``p:not([condition*='Default.Mobile'])``, where you replace ``Default.Mobile`` with the condition you'd like to exclude.

**Can I exclude a file from processing?**
Yes. To exclude a file from processing you create a new text file in the same folder as your topic file and name the file `.mqignore`. The content of the file should be a single line of text matching the name of the topic or snippet to exclude from processing, for example:
```txt
My topic.htm
```
