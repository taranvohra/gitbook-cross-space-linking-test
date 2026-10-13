---
icon: hand-wave
---

# Welcome

## Welcome

Welcome to the GitBook starter template! Here you'll get an overview of all the amazing features GitBook offers to help you build beautiful, interactive documentation.

You'll see some of the best parts of GitBook in action — and find help on how you can turn this template into your own.

#### Jump right in

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td><h4><i class="fa-bolt">:bolt:</i></h4></td><td><strong>Quickstart</strong></td><td>Create your first site</td><td></td><td></td><td></td></tr><tr><td><h4><i class="fa-leaf">:leaf:</i></h4></td><td><strong>Editor basics</strong></td><td>Learn the basics of GitBook</td><td></td><td></td><td></td></tr><tr><td><h4><i class="fa-globe-pointer">:globe-pointer:</i></h4></td><td><strong>Publish your docs</strong></td><td>Share your docs online</td><td></td><td></td><td></td></tr></tbody></table>

##

GitBook has a powerful block-based editor that allows you to seamlessly create, update, and enhance your content.

<figure><img src="https://gitbookio.github.io/onboarding-template-images/editor-hero.png" alt=""><figcaption></figcaption></figure>

#### Writing content

GitBook offers a range of block types for you to add to your content inline — from simple text and tables, to code blocks and more. These elements will make your pages more useful to readers, and offer extra information and context.

Either start typing below, or press `/` to see a list of the blocks you can insert into your page.

#### Add a new block

{% stepper %}
{% step %}
#### Open the insert block menu

Press `/` on your keyboard to open the insert block menu.
{% endstep %}

{% step %}
#### Search for the block you need

Try searching for “Stepper”, for exampe, to insert the stepper block.
{% endstep %}

{% step %}
#### Insert and edit your block

Click or press Enter to insert your block. From here, you’ll be able to edit it as needed.
{% endstep %}
{% endstepper %}

## Markdown

GitBook supports many different types of content, and is backed by Markdown — meaning you can copy and paste any existing Markdown files directly into the editor!

<figure><img src="https://gitbookio.github.io/onboarding-template-images/markdown-hero.png" alt=""><figcaption></figcaption></figure>

Feel free to test it out and copy the Markdown below by hovering over the code block in the upper right, and pasting into a new line underneath.

```markdown
# Heading

This is some paragraph text, with a [link](https://docs.gitbook.com) to our docs.

## Heading 2

-   Point 1
-   Point 2
-   Point 3
```

{% hint style="info" %}
If you have multiple files, GitBook makes it easy to import full repositories too — allowing you to keep your GitBook content in sync.
{% endhint %}

## Images & media

GitBook allows you to add images and media easily to your docs. Simply drag a file into the editor, or use the file manager in the upper right corner to upload multiple images at once.

<figure><img src="https://gitbookio.github.io/onboarding-template-images/images-hero.png" alt=""><figcaption><p>Add alt text and captions to your images</p></figcaption></figure>

{% hint style="info" %}
You can also add images simply by copying and pasting them directly into the editor — and GitBook will automatically add it to your file manager.
{% endhint %}

## Interactive blocks

In addition to the default Markdown you can write, GitBook has a number of out-of-the-box interactive blocks you can use. You can find interactive blocks by pressing `/` from within the editor.

<figure><img src="https://gitbookio.github.io/onboarding-template-images/interactive-hero.png" alt=""><figcaption></figcaption></figure>

#### Tabs

{% tabs %}
{% tab title="First tab" %}
Each tab is like a mini page — it can contain multiple other blocks, of any type. So you can add code blocks, images, integration blocks and more to individual tabs in the same tab block.
{% endtab %}

{% tab title="Second tab" %}
Add images, embedded content, code blocks, and more.

```javascript
const handleFetchEvent = async (request, context) => {
    return new Response({ message: 'Hello World' })
}
```
{% endtab %}
{% endtabs %}

#### Expandable sections

<details>

<summary>Click me to expand</summary>

Expandable blocks are helpful in condensing what could otherwise be a lengthy paragraph. They are also great in step-by-step guides and FAQs.

</details>

#### Embedded content

{% hint style="info" %}
GitBook supports thousands of embedded websites out-of-the-box, simply by pasting their links. Feel free to check out which ones[ are supported natively](https://iframely.com).
{% endhint %}

## Integrations

GitBook integrations allow you to connect your GitBook spaces to some of your favorite platforms and services. You can install integrations into your GitBook page from the _Integrations_ menu in the top left.

<figure><img src="https://gitbookio.github.io/onboarding-template-images/integrations-hero.png" alt=""><figcaption></figcaption></figure>

#### Types of integrations

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th></tr></thead><tbody><tr><td><strong>Analytics</strong></td><td>Track analytics from your docs</td><td><a href="https://www.gitbook.com/integrations#analytics">https://www.gitbook.com/integrations#analytics</a></td><td></td><td></td></tr><tr><td><strong>Support</strong></td><td>Add support widgets to your docs</td><td><a href="https://www.gitbook.com/integrations#support">https://www.gitbook.com/integrations#support</a></td><td></td><td></td></tr><tr><td><strong>Interactive</strong></td><td>Add extra functionality to your docs</td><td><a href="https://www.gitbook.com/integrations#interactive">https://www.gitbook.com/integrations#interactive</a></td><td></td><td></td></tr><tr><td><strong>Visitor Authentication</strong></td><td>Protect your docs and require sign-in</td><td><a href="https://www.gitbook.com/integrations#visitor-authentication">https://www.gitbook.com/integrations#visitor-authentication</a></td><td></td><td></td></tr></tbody></table>
