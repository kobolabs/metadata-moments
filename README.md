#Kobo Metadata Moments - A compilation

What's in this document:
A complilation of all the metadata moments shared by Kobo on the Kobo Publishers’ Newsletter.
 

### Table of Contents

1. [Titles & Subtitles](#titles-&-subtitles)
2. [Publishing Status](#publishing-status)
3. [Category codes](#category-codes)
4. [Be Aware of your Dates](#be-aware-of-your-dates)

## Titles & Subtitles 
 
The `<TitleText>` tag should only include the title. Titles are displayed on our site as they are
submitted in the `<TitleText>`. There are separate tags for subtitle, series information, edition,
and author name - proper use of tags means better discovery on our site. 

   **Best Practices for Title and Subtitle**
   
• Don't include series information in the title - that's what the `<series>` or `<collection>`
composites are for!</br>
• Use the `<subtitle>` tag instead of including the subtitle as part of the main title</br>
• Don't invert titles so that articles are at the end. (e.g. Shark in the Park, The.)</br>
• Don't include the author's name in the title.</br>
• Title and Subtitle have a limit of 250 characters each, including spaces.</br>

  **ONIX 2.1**
  
`<Title>`</br>
`<TitleType>01</TitleType>`</br>
`<TitleText>The Shark In The Park</TitleText>`</br>
`<Subtitle>Left Shark's Park Lark</Subtitle>`</br>
`</Title>`</br>

  **ONIX 3.0**
  
`<TitleDetail>`</br>
`<TitleType>01</TitleType>`</br>
`<TitleElement>`</br>
`<TitleElementLevel>01</TitleElementLevel>`</br>
`<TitlePrefix>The</TitlePrefix>`</br>
`<TitleWithoutPrefix>Shark In The Park</TitleWithoutPrefix>`</br>
`<Subtitle>Left Shark's Park Lark</Subtitle>`</br>
`</TitleElement>`</br>
`</TitleDetail>`</br>


## Publishing Status

**ONIX**

Publishing Status is a simple yet powerful tag in ONIX: it is the composite that can activate or
deactivate a title without manual intervention.
At Kobo, a value of 02 (Forthcoming) or 04 (Active) will activate a title, provided that its
Activation Date is in the past. Any other value will deactivate the title (remove the title from
sale), so we encourage you to review and update your catalogue, paying special attention to
any titles with value 00 (Unspecified).
It’s important to note that Publishing Status is required in ONIX 3.0. And while it’s not required
in ONIX 2.1 it is considered the best practice to include it.

</br>`<PublishingStatus>04</PublishingStatus>`
or
`<b394>04</b394>`</br>

**Excel**

In our excel template, we use column A: Publishing Status. A title will be available for sale or
preorder by using the value active. To remove your title from sale, simply use the value
deactivated.


## Category Codes

A subject category code from the scheme identified (BISAC, BIC, etc) will help catalogue your
ebooks. Category codes help discoverability on site because your chosen codes correspond to
our category stores. In addition to identifying a main subject please include additional subject
codes with increasing precision so your target audience will find your books.

**Best Practices for Category Codes:**

• Kobo requires a main subject code for each title. We recommend using three codes to
improve discoverability.</br>
• Kobo only supports BISAC, BIC, CULTURA, and CLIL categories codes. (Please note that the
CLIL codes are accepted but mapped to BISAC via our system).</br>
• Choose the most specific categories which correspond to your ebooks. The more accurate
categories will be the best. Please don’t use generic category codes (e.g. LCO000000 ->
LITERARY COLLECTIONS / General, instead of a more accurate code such as LCO008020
LITERARY COLLECTIONS / European / French).</br>
• Kobo accepts and stores keywords but does not use them currently for classification.</br>
• Do not mix fiction and non-fiction codes otherwise the metadata will be rejected by our
system.</br>
• Do not use mix kids and adults category codes, otherwise metadata will be rejected by our
system. Our system will reject all metadata with both Kids (JUV and JNF categories) and Adult
content or category for an ebook.</br>
• KIDS STORE: For Kids Store, Juvenile BISAC or BIC codes – JUV or JNF bisac codes, and Y- BIC
codes are required.</br>

**ONIX 2.1 Reference name:**</br>
BISAC</br>
`<BASICMainSubject>JNF001000</BASICMainSubject>`</br>
`<Subject>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
`<SubjectCode>JNF028000</SubjectCode>`</br>
`</Subject>`</br>
BIC</br>
`<BICMainSubject> YNU</BICMainSubject>`</br>


**ONIX 2.1 Short tags**</br>
BISAC</br>
`<subject>`</br>
`<x425/>`</br>
`<b067>10</b067>`</br>
`<b069>JNF001100</b069>`</br>
`<subject>`</br>
`<subject>`</br>
`<b067>10</b067>`</br>
`<b069>JNF028020</b069>`</br>
`</subject>`</br>

BIC</br>
`<b065> YNU</b065>`</br>

**ONIX 3.0 Reference name:**</br>
`<Subject>`</br>
`<MainSubject/>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
`<SubjectCode> JNF001000</SubjectCode>`</br>
`</Subject>`</br>
`<Subject>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>` </br>
`<SubjectCode>JNF028020</SubjectCode>`</br>
`</Subject>`</br>

**ONIX 3.0 short tags:**</br>
`<subject>`</br>
`<x425/>`</br>
`<b067>10</b067>`</br>
`<b069>JNF001100</b069>`</br>
`<subject>`</br>
`<subject>`</br>
`<b067>10</b067>`</br>
`<b069>JNF028020</b069>`</br>
`</subject>`</br>

**NOTE : We only support BISAC, CULTURA, BIC and CLIL.**</br>
'10': 'BISAC',
'12': 'BIC',
'20': 'Keywords',
'29': 'CLIL',
'78': 'C_CODE',
If code is ‘24’ we use what is in `<SubjectSchemeName>`</br>

**Useful links:**
• BISAC category codes : https://www.bisg.org/complete-bisac-subject-headings-2014-edition
• For all BIC subject codes and qualifiers, see http://www.bic.org.uk/7/BIC-Standard-SubjectCategories/
• ONIX Code Lists Issue 27 - Subject scheme identifier code : http://home.bicmedia.com/onix_info/2-1-4/codelists/onix-codelist-27.htm

## Be Aware of your Dates!

Dates matter! This is one of the most important pieces of information to be included in your metadata in order to be sure your titles will be on sale at the right time. You can manage preorders and promotions by effectively using date composites.

#### Best Practice**</br>

**Publication Date**</br>

• Your eBook's publication date is what appears on the product/item page on the
Kobo store. It is a display value only and does not trigger sales.
• If no publication date is included, the default date is set to December 2009. 

**On Sale Date/Embargo date**</br>

• The On Sale Date is when your title is made active on site. If your book is
available for preorder, it is the date it goes from preorder to regular sale. This is
also the date the epub will be available for download to customer libraries.
• If a Publication Date set in the future is provided but an On Sale Date is missing,
the default On Sale Date will match the Publication Date. If the Publication Date
is set in the past or is missing, the default On Sale Date will be the date metadata
is loaded.
*In ONIX 3.0 the Embargo Date should be used as the On Sale Date field is
deprecated.

**Announcement date**</br>

• The date when a new product may be announced to the general public, typically
triggering pre-order status.
• Kobo reads and stores this tag but the functionality is not yet supported. You can
still send metadata as it will be stored until we support this date field.

**Dates in price composites (applies to ONIX metadata only)**</br>

• Price Effective Date composites allow you to schedule promotional prices with
your ONIX feed. 

• Some best practices include:

1.Your starting regular price must have an end date. Otherwise, our system
won’t know to look for a new price.
2.The promo price must have both a start and end date.
3.Your regular price is reinstated by including a new start date. All dates are
inclusive: they start at 0:00 EST and end at 23:59 EST of the specified
date.

