![background sidebar image](https://github.com/kobolabs/metadata-moments/blob/master/banner-openUp.png)

#Kobo Metadata Moments

## Table of Contents
### Metadata
  1. **Title Details**</br>
* [Titles & Subtitles](#titles--subtitles)</br>
* [Related Product](#related-product)</br>
* [Master Brand](#master-brand)</br>
  2. **Categorisation**</br>
* [Audience Ranges](#audience-ranges)</br>
* [Category codes](#category-codes)</br>
* [BISAC codes](#bisac-codes)</br>
* [YAN/YAF BISAC](#yanyaf-bisac)</br>
  3. **Dates**</br>
* [Dates](#dates)
* [Announcement Date](#announcement-date)</br>
* [Price Effective Dates](#price-effective-dates)</br>
  4. **Prices**</br>
* [Prices and Price Type Codes](#prices-and-price-type-codes)</br>
* [TRY pricing tips for Kobo’s launch in Turkey](#try-pricing-tips-for-kobos-launch-in-turkey)</br>
  5. **Sales Rights**</br>
* [Publishing Status](#publishing-status)</br>
* [Sales Rights](#sales-rights) </br>

### Miscellaneous/Other Updates
   * [New country store view on Kobo.com](#new-country-store-view-on-kobocom)</br>

 </br></br>
# Metadata</br>

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

</br></br>
## Related Product

Related Product links a product’s eISBN to its related product identifiers, such as its print ISBN. We strongly recommend sending Related Product information. While Kobo itself does not use the `<RelatedProduct>` composite in our store, many of our partners who sell physical books use it to link the ebook and print product pages, which increases potential for discoverability and sales.
 
For publishers sending Excel metadata, Related ISBN details are conveyed in the “Related ISBN” field. While optional, supplying this information is strongly recommended. Only one related ISBN is allowed per ebook. The Related ISBN must be exactly 13 digits with no spaces in order for our system to process it successfully.
 
In ONIX 2.1 and 3.0, multiple Related Products are permitted, as long as the corresponding ISBNs are different in each Related Product composite.
 
### ONIX 2.1 Composites</br>
 
`<RelatedProduct>`</br>
`<RelationCode>13</RelationCode>`</br>
`<ProductIdentifier>`</br>
`<ProductIDType>15</ProductIDType>`</br>
`<IDValue>9782246731412</IDValue>`</br>
`</ProductIdentifier>`</br>
`<ProductForm>BA</ProductForm>`</br>
`</RelatedProduct>`</br>
 
__Short Tags:——</br>
`<relatedproduct>`</br>
`<h208>13</h208>`</br>
`<productidentifier>`</br>
`<b221>15</b221>`</br>
`<b244>9783540261698</b244>`</br>
`</productidentifier>`</br>
`<b012>BA</b012>`</br>
`</relatedproduct>`</br>
 
### ONIX 3.0 Composites</br>
 
`<RelatedProduct>`</br>
`<ProductRelationCode>13</ProductRelationCode>`</br>
`<ProductIdentifier>`</br>
`<ProductIDType>15</ProductIDType>`</br>
`<IDValue>9782246731412</IDValue>`</br>
`</ProductIdentifier>`</br>
`<ProductForm>BA</ProductForm>`</br>
`</RelatedProduct>`</br>
 
 __Short Tags:__</br>
`<relatedproduct>`</br>
`<x455>13</x455>`</br>
`<productidentifier>`</br>
`<b221>15</b221>`</br>
`<b244>9783540261698</b244>`</br>
`</productidentifier>`</br>
`<b012>BA</b012>`</br>
`</relatedproduct>`</br>

### Notes:</br>
* RelationCode and ProductRelationCode 13 equals ePublication based on (print product)
* ProductIDType 15 equals ISBN-13
* ProductForm BA equals Book

</br></br>
## Master Brand 
 
Master Brand refers to a specific character, name or title that exists across multiple series and product forms, and possibly multiple imprints or publishers. It is important to note that Master Brand is not limited to books. This designation is helpful when trying to improve the discoverability of your title, specifically children’s titles featuring popular characters (e.g. Winnie the Pooh). This can be nested within a collection or series. Currently Kobo only sorts by Master Brand in the kids' store, but we store information for all products.
 
__Using ONIX 2.1__, Master Brand is provided with the following composite:
 </br>
`<OtherText>` </br>
`<TextTypeCode>98</TextTypeCode>` </br>
`<Text>Jack Reacher</Text>` </br>
`</OtherText>` </br>

__Using ONIX 3.0__, the following composite is used:</br>    
`<TitleDetail>` </br>
`<TitleType>01<\TitleType>` </br>
`<TitleElement>` </br>
`<TitleElementLevel>05</TitleElementLevel>` </br>
`<TitleText>Jack Reacher</TitleText>` </br>
`</TitleElement>` </br>
`</TitleDetail>` </br>
 </br>
In Kobo’s Excel template, simply input Master Brand information into the Main Character (brand) column. 

</br></br>
## Audience Ranges

Audience Range indicates the intended audience or readership age for a product. You may send
a minimum age (“From”), a maximum age (“To”) or a range (“From” and “To”). Kobo uses an
Audience Range Qualifier of 17 (Interest Age) and an age range between 0-17 to determine
eligibility for our Kids’ Store. While Age Range is not required in ONIX 3.0 or ONIX 2.1 it is the
best practice to include it.

  **Common Errors:**
* Representing a number with a text value (e.g. "sixteen" rather than "16”).
* Adding characters that are not numbers (e.g. "18+" or “18 and up” rather than "18").</br>
  
__Onix 2.1 and 3.0 Composite:__</br>
For example, the following composite tells us that this title is for Interest Ages 8-12:
</br>`<audiencerange>`</br>
`<b074>17</b074>`</br>
`<b075>03</b075>` {Indicates “from”}</br>
`<b076>8</b076>` {Indicates minimum age}</br>
`<b075>04</b075>` {Indicates “to”}</br>
`<b076>12</b076>` {Indicates maximum age}</br>
`</audiencerange>`</br>


This example tells us this title is for Interest Ages 6+:</br>
`<AudienceRange>`</br>
`<AudienceRangeQualifier>17</AudienceRangeQualifier>`</br>
`<AudienceRangePrecision>03</AudienceRangePrecision>`</br>
`<AudienceRangeValue>6</AudienceRangeValue>`</br>
`</AudienceRange>`</br>

</br>
</br>
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
`<BICMainSubject>YNU</BICMainSubject>`</br>


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
'10': 'BISAC',</br>
'12': 'BIC',</br>
'20': 'Keywords',</br>
'29': 'CLIL',</br>
'78': 'C_CODE',</br>
If code is ‘24’ we use what is in `<SubjectSchemeName>`</br>

**Useful links:**</br>
• BISAC category codes : https://www.bisg.org/complete-bisac-subject-headings-2014-edition</br>
• For all BIC subject codes and qualifiers, see http://www.bic.org.uk/7/BIC-Standard-SubjectCategories/</br>
• ONIX Code Lists Issue 27 - Subject scheme identifier code : http://home.bicmedia.com/onix_info/2-1-4/codelists/onix-codelist-27.htm

</br>
</br>
## BISAC Codes
 
Having accurate category codes ensures that books are properly categorized in our store, making discoverability easier for customers. While we accept BIC and CLIL category codes as well, BISAC is the most common category code we receive, and our categorization structure is based on BISAC. Kobo accepts the complete 2015 BISAC list published by BISG, including the new young adult (YAF and YAN) categories.
 
For publishers sending Excel metadata, category codes, including BISAC codes, are to be entered in the three “Categorization Code” and “Categorization Type” fields. The “Categorization Code” field is for the BISAC code itself (ex. FIC000000), while the “Categorization Type” field is for the type of category code you are using (ex. BISAC). Only one category code is permitted per cell. The BISAC code in the first “Categorization Code” field will be the book’s primary category.
 
Kobo will display up to three category codes on a book’s product page, and we suggest you send three per product, with increasing precision, to ensure your target audience will find your books. While ONIX 2.1 and 3.0 allow for more than three category codes, only the first three categories listed will be shown on a product page.

### ONIX 2.1 Composites</br>
`<BASICMainSubject>YAF022000</BASICMainSubject>`</br>
</br>
`<Subject>`</br>
 `<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
 `<SubjectCode>YAF042000</SubjectCode>`</br>
`</Subject>`</br>

__Short Tags:__</br>
`<b064>YAF022000</b064>`</br>
</br>
`<Subject>`</br>
`<b067>10</b067>`</br>
`<b069>YAF042000</b069>`</br>
`</Subject>`</br>

### ONIX 3.0 Composites</br>
`<Subject>`</br>
`<MainSubject/>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
`<SubjectCode>YAF022000</SubjectCode>`</br>
`</Subject>`</br>
</br>
`<Subject>`</br>
 `<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
 `<SubjectCode>YAF042000</SubjectCode>`</br>
`</Subject>`</br>

__Short Tags:__</br>
`<Subject>`</br>
`<x425/>`</br>
`<b067>10</b067>`</br>
`<b069>YAF022000</b069>`</br>
`</Subject>`</br>
</br>
`<Subject>`</br>
`<b067>10</b067>`</br>
`<b069>YAF042000</b069>`</br>
`</Subject>`</br>

* `<BASICMainSubject>` = the primary category code (ONIX 2.1)
* `<MainSubject/>` = the primary category code (ONIX 3.0)
* `<SubjectSchemeIdentifier>` = category type
* `<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>` = BISAC category type
* `<Subject Code>` = category code

</br></br>
## YAN/YAF BISAC
 
In 2015, BISG introduced Young Adult Fiction (YAF) and Young Adult Nonfiction (YAN) subject codes to replace JNF and JUV codes aimed at young adult readers. Kobo accepts all YAF and YAN BISAC codes. Like JNF and JUV codes, using accurate YAF and YAN BISAC codes will allow books to be included in our kids’ store. The new YA BISAC codes make it easier for a growing customer base of young adult readers to discover new books on Kobo.
 
As with all other BISAC codes, publishers sending Excel metadata can enter YAF and YAN codes into the three “Categorization Code” fields.
 
### __Tips:__
YAF and YAN BISAC codes should be assigned to books aimed at ages 12-18 and grades 7-12.
Basic mapping from the JUV and JNF BISAC codes to the new YAF and YAN BISAC Codes is included in the BISAC 2015 and 2016 Edition packages.
Please do not mix young adult BISAC codes with juvenile or adult BISAC codes.
 
### __Links:__
YAF Codes: http://bisg.org/page/YAFiction</br>
YAN Codes: http://bisg.org/page/YANonFiction
 
### __ONIX 2.1 and 3.0 Composites using YAF:__</br>
`<Subject>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
`<SubjectCode>YAF042000</SubjectCode>`</br>
`</Subject>`</br>

__Short Tags:__</br>
`<Subject>`</br>
`<b067>10</b067>`</br>
`<b069>YAF042000</b069>`</br>
`</Subject>`</br>

### ONIX 2.1 and 3.0 Composites using YAN:</br>
`<Subject>`</br>
`<SubjectSchemeIdentifier>10</SubjectSchemeIdentifier>`</br>
`<SubjectCode>YAN006050</SubjectCode>`</br>
`</Subject>`</br>

__Short Tags:__</br>
`<Subject>`</br>
`<b067>10</b067>`</br>
`<b069>YAN006050</b069>`</br>
`</Subject>`</br>

</br></br>
## Dates

This is one of the most important pieces of information to be included in your metadata in order to be sure your titles will be on sale at the right time. You can manage preorders and promotions by effectively using date composites.

#### Best Practice</br>

**_Publication Date_**</br>

• Your eBook's publication date is what appears on the product/item page on the
Kobo store. It is a display value only and does not trigger sales.</br>
• If no publication date is included, the default date is set to December 2009. 

**_On Sale Date/Embargo date_**</br>

• The On Sale Date is when your title is made active on site. If your book is
available for preorder, it is the date it goes from preorder to regular sale. This is
also the date the epub will be available for download to customer libraries.</br>
• If a Publication Date set in the future is provided but an On Sale Date is missing,
the default On Sale Date will match the Publication Date. If the Publication Date
is set in the past or is missing, the default On Sale Date will be the date metadata
is loaded.</br>
_In ONIX 3.0 the Embargo Date should be used as the On Sale Date field is
deprecated._

**_Announcement date_**</br>

• The date when a new product may be announced to the general public, typically
triggering pre-order status.</br>
• Kobo reads and stores this tag but the functionality is not yet supported. You can
still send metadata as it will be stored until we support this date field.

**_Dates in price composites (applies to ONIX metadata only)_**</br>

• Price Effective Date composites allow you to schedule promotional prices with your ONIX feed. </br>

• Some best practices include:</br>
  * Your starting regular price must have an end date. Otherwise, our system
won’t know to look for a new price.</br>
  * The promo price must have both a start and end date.</br>
  * Your regular price is reinstated by including a new start date. All dates are
inclusive: they start at 0:00 EST and end at 23:59 EST of the specified
date.

**Tags:**</br>
• **_Publication Date_** </br>

ONIX 2.1</br>
Reference name:</br>
`<PublicationDate>20130315</PublicationDate>`</br>
Short tag:</br>
`<b003>20130315</b003>`</br>

ONIX 3.0</br>
Reference name:</br>
`<PublishingDate>`</br>
`<PublishingDateRole>01</PublishingDateRole>`</br>
`<Date>20150919</Date>`</br>
`</PublishingDate>`</br>
Short tag:</br>
`<publishingdate>`</br>
`<x448>01</x448>`</br>
`<b306>20150919</b306>`</br>
`</publishingdate>`</br>

Excel
Publication Date: 2015-09-19

• **_On Sale Date/Embargo date_**</br>

ONIX 2.1 (On Sale Date)</br>
Reference name:</br>
`<OnSaleDate>20150219</OnSaleDate>`</br>
Short tag:</br>
`<j143>20150219</j143>`

ONIX 3.0 (Embargo Date):</br>
Reference name:</br>
`<PublishingDate>`</br>
`<PublishingDateRole>02</PublishingDateRole>`</br>
`<Date>20150219</Date>`</br>
`</PublishingDate>`</br>
Short tag:</br>
`<publishingdate>`</br>
`<x448>02</x448>`</br>
`<b306>20150219</b306>`</br>
`</publishingdate>`</br>

Excel</br>
OnSale Date: 2015-02-19

• **_Announcement date_**</br>

ONIX 3.0</br>
Reference name:</br>
`<PublishingDate>`</br>
`<PublishingDateRole>09</PublishingDateRole>`</br>
`<Date>20150219</Date>`</br>
`</PublishingDate>`</br>
Short tag:</br>
`<publishingdate>`</br>
`<x448>09</x448>`</br>
`<b306>20150219</b306>`</br>
`</publishingdate>`</br>

Excel
Announcement Date: 2015-02-19

#### • **_Price Effective Dates [ONIX only]_** </br>

ONIX 2.1 example (with embedded notes for clarification):</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>7.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j162>20151222</j162>`</br>
`</price>`</br>
**--- the above price will end at 23:59 EST on Dec 22**</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>3.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j161>20151223</j161>`</br>
`<j162>20151230</j162>`</br>
`</price>`</br>
**--- the promo price starts at 0:00 EST Dec 23 and ends 23:59 EST Dec 30**</br>
`<price>`</br>
`<j148>41</j148>`</br>
`<j151>7.99</j151>`</br>
`<j152>USD</j152>`</br>
`<j161> 20151231</j161>`</br>
`</price>`</br>
**--- the regular price is reinstated at 0:00 EST Dec 31</br>
Onix 3.0 uses the PriceDateRole tags where PriceDateRole 14 = From Date and PriceDateRole 15 = Until Date**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>10.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>15</PriceDateRole>`</br>
`<Date>20151221</Date>`</br>
`</PriceDate>`</br>
`</Price>`</br>
**--- the above price will end at 23:59 EST on Dec 21**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>8.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>14</PriceDateRole>`</br>
`<Date>20151222</Date>`</br>
`</PriceDate>`</br>
`<PriceDate>`</br>
`<PriceDateRole>15</PriceDateRole>`</br>
`<Date>20151230</Date>`</br>
`</PriceDate>`</br>
`</Price>`</br>
**--- the promo price starts at 0:00 EST on Dec 22 and ends 23:59 EST Dec 30**</br>
`<Price>`</br>
`<PriceType>01</PriceType>`</br>
`<PriceAmount>10.00</PriceAmount>`</br>
`<CurrencyCode>USD</CurrencyCode>`</br>
`<PriceDate>`</br>
`<PriceDateRole>14</PriceDateRole>`</br>
`<Date>20151231</Date> </PriceDate>`</br>
`</Price>`</br>
**--- the regular price is reinstated at 0:00 EST on Dec 31**</br>

</br>
</br>
## Announcement Date
 
Announcement Date is the day that your product may first be made available for sale to the public. Used most often with preorders, this is the first day that the preorder page will be available on Kobo. If you plan to use announcement date to control the availability of a preorder, please ensure this date is set before the On Sale Date, otherwise the preorder period will not be valid. If no announcement date is provided, your preorder will be available when the metadata and cover are loaded.
 
Using ONIX 3.0, Announcement Date is provided with the following composite:
 </br>
`<PublishingDate>`</br>
`<PublishingDateRole>09<PublishingDateRole>`</br>
`<Date>20150109</Date>`</br>
`</PublishingDate>`</br>
 
* See [List 163](http://www.bic-media.com/dmrn/codelists/onix-codelist-163.htm): Publishing Date Role
* Onix 2.1 does not have a composite for Announcement Date.
* Publishers sending excel metadata can indicate Announcement Date in column Y of the excel template.

</br></br>
## Master Brand 
 
Master Brand refers to a specific character, name or title that exists across multiple series and product forms, and possibly multiple imprints or publishers. It is important to note that Master Brand is not limited to books. This designation is helpful when trying to improve the discoverability of your title, specifically children’s titles featuring popular characters (e.g. Winnie the Pooh). This can be nested within a collection or series. Currently Kobo only sorts by Master Brand in the kids' store, but we store information for all products.
 
__Using ONIX 2.1__, Master Brand is provided with the following composite:
 </br>
`<OtherText>` </br>
`<TextTypeCode>98</TextTypeCode>` </br>
`<Text>Jack Reacher</Text>` </br>
`</OtherText>` </br>

__Using ONIX 3.0__, the following composite is used:</br>    
`<TitleDetail>` </br>
`<TitleType>01<\TitleType>` </br>
`<TitleElement>` </br>
`<TitleElementLevel>05</TitleElementLevel>` </br>
`<TitleText>Jack Reacher</TitleText>` </br>
`</TitleElement>` </br>
`</TitleDetail>` </br>
 </br>
In Kobo’s Excel template, simply input Master Brand information into the Main Character (brand) column. 

</br></br>
## Price Effective Dates
 
Price effective dates allow you to schedule price changes in advance in your ONIX feed. This composite is especially useful for price promotions — you can schedule the dates of the price drop and return to regular price in the same ONIX feed.
 
__Requirements to schedule a price promo:__

* Ensure your starting regular price has an end date. Otherwise, our system won’t know to look for a new price.
* Ensure the promo price has both a start and end date.
* Ensure your regular price is reinstated by including a new start date. All dates are inclusive: they start at 0:00 EST and end at 23:59 EST of the specified date.

[Click here](#-price-effective-dates-onix-only-) for example of a sample scheduled price reduction, with embedded comments for clarification.

</br></br>
## Prices and Price Type Codes
 
When sending multiple prices for your books, it’s important to use the correct price type code in order for prices to display properly in each territory. Price type codes specify the type of price submitted (e.g. agency, wholesale, IPP) and indicates if the price includes or excludes tax.
 
The field is `<PriceTypeCode>` in ONIX 2.1 and `<PriceType>` in ONIX 3.0.
 
__Prices without tax included (CA and US)__
 
01 – Wholesale prices in Canada and the US, without tax included
41 – Agency prices in Canada and the US, without tax included
03 – IPP prices in Canada and the US, without tax included
 
__Prices with tax included (EU, UK, and AU)__
 
02 – Wholesale prices in the EU, UK, and AU, with tax included
42 – Agency prices in the EU, UK, and AU, with tax included
04 – IPP prices in the EU, UK, and AU, with tax included
 
Remember: Publishers must submit prices that correspond with their territory and contract type.
 
#### Best Practices
Use periods or commas to indicate decimals but DO NOT use both.
Use whole numbers for Japanese yen (JPY) prices and Mexican pesos (MXN) — no decimals, please!
Free books can be submitted as 0.00 or 0.
Avoid sending 0.01 prices or no prices or your metadata update will fail.
 
#### Reminders for Excel Publishers
Format prices as Numbers (not ‘General’).
Do not include currency symbols (e.g. $).
Use upper-case letters for currency codes.
 
#### Examples of Correct Usage

  * Excel
Note: Excel publishers do not need to specify price type codes. Publishers populate the price and currency fields, and Kobo will automatically use the correct code.
 
Price: 7.99
Currency: CAD

  * ONIX 2.1</br>
`<price>`</br>
`<j148 refname="PriceTypeCode">04</j148>`</br>
`<j151 refname="PriceAmount">3.99</j151>`</br>
`<j152 refname="CurrencyCode">EUR</j152>`</br>
`</price>`</br>

  * ONIX 3.0</br>
`<price>`</br>
`<j148 refname="PriceType">01</j148>`</br>
`<j151 refname="PriceAmount">3.99</j151>`</br>
`<j152 refname="CurrencyCode">USD</j152>`</br>
`</price>`</br>

</br>
</br>
## TRY pricing tips for Kobo’s launch in Turkey

In light of our recent launch in Turkey, we are encouraging publishers with TR territory rights to consider including TRY prices in their metadata.  

Some things to keep in mind if you’re planning to send TRY prices:
Prices will be displayed with decimals included. (E.g. 1,000.99 TRY). They should not contain commas.
TRY prices delivered via Kobo’s Excel template will be treated as tax-in prices in Turkey.
Turkey is a VAT-inclusive territory, as such we recommend that prices delivered via ONIX be sent with the appropriate tax-in price types (02 for wholesale, 42 for agency). Please see examples below: 

### ONIX 2.1</br>
`<price>`</br>
`<PriceTypeCode>42</PriceTypeCode>`</br>
`<PriceAmount>1000.99</PriceAmount>`</br>
`<CurrencyCode>TRY</CurrencyCode>`</br>
`<CountryCode>TR</CountryCode>`</br>
`</price>`</br>
 
### ONIX 3.0</br>
`<Price>`</br>
`<PriceType>42</PriceType>`</br>
`<PriceAmount>1000.99</PriceAmount>`</br>
`<CurrencyCode>TRY</CurrencyCode>`</br>
`<Territory>`</br>
`<CountriesIncluded>TR</CountriesIncluded>`</br>
`</Territory>`</br>
`</Price>`</br>
 
__Please note:__ If a publisher does not have the capability to include TRY prices in their metadata, depending on your agreement with Kobo, we will continue to convert from the list price and currency with TR territory rights into the local Turkish price.
</br>
</br>
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

`<PublishingStatus>04</PublishingStatus>`</br>
or
`<b394>04</b394>`</br>

**Excel**

In our excel template, we use column A: Publishing Status. A title will be available for sale or
preorder by using the value active. To remove your title from sale, simply use the value
deactivated.

</br>
</br>
## Sales Rights

The Sales Rights `<SalesRights>` composite is one of the most important ONIX fields in the metadata and should be carefully completed to respect publishing rights. The Sales Rights composite is a group of tags that specify the territorial sales rights chosen by the publisher for a given book, at a global product level. Publishers should clearly state the countries in which a product can be sold. You can also exclude specific countries if needed.
 
### Best Practices
The Sales Rights composite is a mandatory field in Onix 2.1 and 3.0. If the Sales Rights are missing in the metadata provided, the metadata will fail and not be ingested by our system.
Please note that Kobo only supports 3 types of `<SalesRightsType>` (`<b089>`) values:</br>
  * 01 - for sale (exclusive rights)</br>
  * 02 - for sale (non-exclusive rights)</br>
  * 03 - not for sale</br>

You can consult the following the List 46: Sales rights type code: http://home.bic-media.com/onix_info/2-1-4/codelists/onix-codelist-46.htm
To indicate sales rights use two-letter territory codes to specify where your ebook can be sold according to the rights your company holds. `<SalesRightsType>` is important in indicating specific type of rights held (exclusive, non-exclusive, not for sale, etc). Please see correct usage for how to declare sales rights in ONIX.

### ONIX 2.1: </br>
Please use upper-case characters and separate each territory with a space in `<RightsCountry>US CA</RightsCountry>`. World Rights should be indicated as `<RightsTerritory>WORLD</RightsTerritory>` https://www.medra.org/stdoc/onix-codelist-91.htm

### ONIX 3.0:</br>
Similarly, in `<CountriesIncluded>` please use upper-case characters and separate each territory with a space. World rights should be indicated as `<RegionsIncluded>WORLD</RegionsIncluded>` https://www.medra.org/stdoc/onix-codelist-91.htm 
Excel (column V Excel template): Leave this field blank if you have world rights. If your eBook can only be sold in a specific list of countries, you must indicate their two-letter country codes in this field with each country code separated by a comma. For example: CA, US, GB</br>

</br>
</br>
#  Miscellaneous/Other Updates</br>

## New country store view on Kobo.com
 
You may have noticed that we have recently made some adjustments to our store page at www.kobo.com. You can now see how our store looks in different countries throughout the world. When you first visit the online store, you will see a welcome screen where you can choose your country. You can also change your country by clicking on the flag icon on our main page, and can now choose from 36 different countries.
 
[Try it out >](http://kobo.us5.list-manage.com/track/click?u=c032db3d20aa5ba495901131a&id=af4b6a1be6&e=899d096d2f)

