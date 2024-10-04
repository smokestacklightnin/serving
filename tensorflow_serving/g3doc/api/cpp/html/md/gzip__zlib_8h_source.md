::: {#top}
::: {#titlearea}
+-----------------------------------------------------------------------+
| ::: {#projectname}                                                    |
| My Project                                                            |
| :::                                                                   |
+-----------------------------------------------------------------------+
:::

::: {#main-nav}
:::

::: {#MSearchSelectWindow onmouseover="return searchBox.OnSearchSelectShow()" onmouseout="return searchBox.OnSearchSelectHide()" onkeydown="return searchBox.OnSearchSelectKey(event)"}
:::

::: {#MSearchResultsWindow}
:::

::: {#nav-path .navpath}
-   [tensorflow\_serving](dir_bbc8937306723ff096d79d77f4a73363.html){.el}
-   [util](dir_1303efdc8de326749a332c6a57186055.html){.el}
-   [net\_http](dir_3615685a5307a228eaa5ec677f0aeb77.html){.el}
-   [compression](dir_52576b27cc816f040ae9dee864b1e6f4.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
gzip\_zlib.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2018 Google Inc. All Rights
Reserved.]{.comment}
:::

::: {.line}
[]{#l00002}[ 2]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00003}[ 3]{.lineno} [Licensed under the Apache License, Version 2.0
(the \"License\");]{.comment}
:::

::: {.line}
[]{#l00004}[ 4]{.lineno} [you may not use this file except in compliance
with the License.]{.comment}
:::

::: {.line}
[]{#l00005}[ 5]{.lineno} [You may obtain a copy of the License
at]{.comment}
:::

::: {.line}
[]{#l00006}[ 6]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00007}[ 7]{.lineno} [
http://www.apache.org/licenses/LICENSE-2.0]{.comment}
:::

::: {.line}
[]{#l00008}[ 8]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00009}[ 9]{.lineno} [Unless required by applicable law or agreed to
in writing, software]{.comment}
:::

::: {.line}
[]{#l00010}[ 10]{.lineno} [distributed under the License is distributed
on an \"AS IS\" BASIS,]{.comment}
:::

::: {.line}
[]{#l00011}[ 11]{.lineno} [WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied.]{.comment}
:::

::: {.line}
[]{#l00012}[ 12]{.lineno} [See the License for the specific language
governing permissions and]{.comment}
:::

::: {.line}
[]{#l00013}[ 13]{.lineno} [limitations under the License.]{.comment}
:::

::: {.line}
[]{#l00014}[
14]{.lineno} [==============================================================================\*/]{.comment}
:::

::: {.line}
[]{#l00015}[ 15]{.lineno} 
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_COMPRESSION\_GZIP\_ZLIB\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_COMPRESSION\_GZIP\_ZLIB\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<zlib.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<cstdint\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[
[27](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html){.line}]{.lineno} [class
]{.keyword}[GZipHeader](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html){.code}
{
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
[GZipHeader](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html){.code}()
{ Reset(); }
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
\~[GZipHeader](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html){.code}()
{}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [// Wipe the slate clean and start from
scratch.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [void]{.keywordtype} Reset() {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  state\_ = IN\_HEADER\_ID1;
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  flags\_ = 0;
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  extra\_length\_ = 0;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  }
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [enum]{.keyword} Status {
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  INCOMPLETE\_HEADER,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  COMPLETE\_HEADER,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  INVALID\_HEADER,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  };
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// If the bytes we\'ve seen so far do not
yet constitute a complete gzip]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// header, return INCOMPLETE\_HEADER. If
these bytes do not constitute a valid]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// gzip header, return INVALID\_HEADER. When
we\'ve seen a complete]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// gzip header, return COMPLETE\_HEADER and
set the pointer pointed]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// to by header\_end to the first byte
beyond the gzip header.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  Status ReadMore([const]{.keyword}
[char]{.keywordtype} \*inbuf, [int]{.keywordtype} inbuf\_len,
[const]{.keyword} [char]{.keywordtype} \*\*header\_end);
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [enum]{.keyword} { [// flags (see
RFC)]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  FLAG\_FTEXT = 0x01, [// bit 0 set: file
probably ascii text]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  FLAG\_FHCRC = 0x02, [// bit 1 set: header CRC
present]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  FLAG\_FEXTRA = 0x04, [// bit 2 set: extra
field present]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  FLAG\_FNAME = 0x08, [// bit 3 set: original
file name present]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  FLAG\_FCOMMENT = 0x10, [// bit 4 set: file
comment present]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  FLAG\_RESERVED = 0xE0, [// bits 5..7:
reserved]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  };
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [enum]{.keyword} State {
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// The first 10 bytes are the fixed-size
header:]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  IN\_HEADER\_ID1,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  IN\_HEADER\_ID2,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  IN\_HEADER\_CM,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  IN\_HEADER\_FLG,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  IN\_HEADER\_MTIME\_BYTE\_0,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  IN\_HEADER\_MTIME\_BYTE\_1,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  IN\_HEADER\_MTIME\_BYTE\_2,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  IN\_HEADER\_MTIME\_BYTE\_3,
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  IN\_HEADER\_XFL,
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  IN\_HEADER\_OS,
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  IN\_XLEN\_BYTE\_0,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  IN\_XLEN\_BYTE\_1,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  IN\_FEXTRA,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  IN\_FNAME,
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  IN\_FCOMMENT,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  IN\_FHCRC\_BYTE\_0,
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  IN\_FHCRC\_BYTE\_1,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  IN\_DONE,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  };
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [int]{.keywordtype} state\_; [// our current
State in the parsing FSM: an int so we can ++]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  uint8\_t flags\_; [// the flags byte of the
header (\"FLG\" in the RFC)]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  uint16\_t extra\_length\_; [// how much of
the \"extra field\" we have yet to read]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} };
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[
[94](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.line}]{.lineno} [class
]{.keyword}[ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.code}
{
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
[ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.code}();
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
\~[ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html){.code}();
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// The max length of the buffer to store
uncompressed data]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [static]{.keyword} constexpr int64\_t
kMaxUncompressedBytes = 100 \* 1024 \* 1024; [// 100MB]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// Wipe a ZLib object to a virgin state.
This differs from Reset()]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// in that it also breaks any dictionary,
gzip, etc, state.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [void]{.keywordtype} Reinit();
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// Call this to make a zlib buffer as good
as new. Here\'s the only]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// case where they differ:]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// CompressChunk(a); CompressChunk(b);
CompressChunkDone(); vs]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [// CompressChunk(a); Reset();
CompressChunk(b); CompressChunkDone();]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// You\'ll want to use Reset(), then, when
you interrupt a compress]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// (or uncompress) in the middle of a chunk
and want to start over.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [void]{.keywordtype} Reset();
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// By default UncompressAtMostOrAll will
return Z\_OK upon hitting the end of]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// the input stream. This function modifies
that behavior by returning]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// Z\_STREAM\_END instead. This is useful
when getting multiple compressed]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// documents in a single stream. Returning
Z\_STREAM\_END will indicate the end]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// of a document.]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [void]{.keywordtype} SetDontHideStreamEnd();
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// Sets the compression level to be
used]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [void]{.keywordtype}
SetCompressionLevel([int]{.keywordtype} level) {
settings\_.compression\_level\_ = level; }
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// Sets the size of the window (history
buffer) used by the compressor.]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// The size is expressed in bits (log base
2 of the desired size).]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [void]{.keywordtype}
SetCompressionWindowSizeInBits([int]{.keywordtype} bits) {
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  settings\_.window\_bits\_ = bits;
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  }
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [// Controls the amount of memory used by
the compresser.]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// Legal value are 1 through 9. See zlib.h
for more info.]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [void]{.keywordtype}
SetCompressionMemLevel([int]{.keywordtype} level) {
settings\_.mem\_level\_ = level; }
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// According to the zlib manual, when you
Compress, the destination]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// buffer must have size at least src +
.1%\*src + 12. This function]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// helps you calculate that. Augment this
to account for a potential]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// gzip header and footer, plus a few bytes
of slack.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [static]{.keyword} uLong
MinCompressbufSize(uLong uncompress\_size) {
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [return]{.keywordflow} uncompress\_size +
uncompress\_size / 1000 + 40;
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  }
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// The minimum size of footers written by
CompressChunkDone().]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [int]{.keywordtype} MinFooterSize()
[const]{.keyword};
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [// Compresses the source buffer into the
destination buffer.]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// sourceLen is the byte length of the
source buffer.]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// Upon entry, destLen is the total size of
the destination buffer,]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [// which must be of size at least
MinCompressbufSize(sourceLen).]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// Upon exit, destLen is the actual size of
the compressed buffer.]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// This function can be used to compress a
whole file at once if the]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// input file is mmap\'ed.]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// Returns Z\_OK if success, Z\_MEM\_ERROR
if there was not]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// enough memory, Z\_BUF\_ERROR if there
was not enough room in the]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// output buffer. Note that if the output
buffer is exactly the same]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [// size as the compressed result, we still
return Z\_BUF\_ERROR.]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [// (check CL\#1936076)]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [// If the values of \*destLen or sourceLen
do not fit in an unsigned int,]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// Z\_BUF\_ERROR is returned.]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [int]{.keywordtype} Compress(Bytef \*dest,
uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  uLong sourceLen);
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [// Uncompresses the source buffer into the
destination buffer.]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [// The destination buffer must be long
enough to hold the entire]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [// decompressed contents.]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// Returns Z\_OK on success, otherwise, it
returns a zlib error code.]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [// If the values of \*destLen or sourceLen
do not fit in an unsigned int,]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [// Z\_BUF\_ERROR is returned.]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [int]{.keywordtype} Uncompress(Bytef \*dest,
uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  uLong sourceLen);
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [// Get the uncompressed size from the gzip
footer. Returns 0 if source is too]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// short (len \< 5).]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  uLongf
GzipUncompressedLength([const]{.keyword} Bytef \*source, uLong len);
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [// Special helper function to help
uncompress gzipped documents:]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [// We\'ll allocate (via std::allocator) a
destination buffer exactly big]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [// enough to hold the gzipped content. We
set dest and destLen.]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [// If we don\'t return Z\_OK, \*dest will
be NULL, otherwise you]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// should free() it when you\'re done with
it.]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [// Returns Z\_OK on success, otherwise, it
returns a zlib error code.]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [// Its the responsibility of the user to
set \*destLen to the]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [// expected maximum size of the
uncompressed data. The size of the]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [// uncompressed data is read from the
compressed buffer gzip footer.]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// This value cannot be trusted, so we
compare it to the expected]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// maximum size supplied by the user,
returning Z\_MEM\_ERROR if its]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [// greater than the expected maximum
size.]{.comment}
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [int]{.keywordtype}
UncompressGzipAndAllocate(Bytef \*\*dest, uLongf \*destLen,
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [const]{.keyword} Bytef \*source, uLong
sourceLen);
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} 
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [// Streaming compression and decompression
methods.]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// {Unc,C}ompressAtMost() decrements
sourceLen by the amount of data that was]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [// consumed: if it returns Z\_BUF\_ERROR,
set the source of the next]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [// {Unc,C}ompressAtMost() to the unconsumed
data.]{.comment}
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} 
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [// Compresses data one chunk at a time \--
ie you can call this more]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// than once. This is useful for a
webserver, for instance, which]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [// might want to use chunked encoding with
compression. To get this]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// to work you need to call start and
finish routines.]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [// Returns Z\_OK if success, Z\_MEM\_ERROR
if there was not]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [// enough memory, Z\_BUF\_ERROR if there
was not enough room in the]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [// output buffer.]{.comment}
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} 
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [int]{.keywordtype} CompressAtMost(Bytef
\*dest, uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  uLong \*sourceLen);
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} 
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  [// Emits gzip footer information, as
needed.]{.comment}
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [// destLen should be at least
MinFooterSize() long.]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [// Returns Z\_OK, Z\_MEM\_ERROR, and
Z\_BUF\_ERROR as in CompressChunk().]{.comment}
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [int]{.keywordtype} CompressChunkDone(Bytef
\*dest, uLongf \*destLen);
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// Uncompress data one chunk at a time \--
ie you can call this]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [// more than once. To get this to work you
need to call per-chunk]{.comment}
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  [// and \"done\" routines.]{.comment}
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  [// Returns Z\_OK if success, Z\_MEM\_ERROR
if there was not]{.comment}
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  [// enough memory, Z\_BUF\_ERROR if there
was not enough room in the]{.comment}
:::

::: {.line}
[]{#l00223}[ 223]{.lineno}  [// output buffer.]{.comment}
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} 
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  [int]{.keywordtype} UncompressAtMost(Bytef
\*dest, uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00226}[ 226]{.lineno}  uLong \*sourceLen);
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [// Checks gzip footer information, as
needed. Mostly this just]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  [// makes sure the checksums match. Whenever
you call this, it]{.comment}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  [// will assume the last 8 bytes from the
previous UncompressChunk]{.comment}
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  [// call are the footer. Returns true iff
everything looks ok.]{.comment}
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [bool]{.keywordtype} UncompressChunkDone();
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [// Only meaningful for chunked
compressing/uncompressing. It\'s true]{.comment}
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [// after initialization or reset and before
the first chunk of]{.comment}
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  [// user data is received.]{.comment}
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  [bool]{.keywordtype} first\_chunk()[ const
]{.keyword}{ [return]{.keywordflow} first\_chunk\_; }
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} 
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  [// Convenience method to check if a
bytestream has a header. This]{.comment}
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  [// is intended as a quick test: \"Is this
likely a GZip file?\"]{.comment}
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  [static]{.keyword} [bool]{.keywordtype}
HasGzipHeader([const]{.keyword} [char]{.keywordtype} \*source,
[int]{.keywordtype} sourceLen);
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} 
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  [// Have we parsed the complete gzip footer?
When this result is true, it is]{.comment}
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [// time to call IsGzipFooterValid() /
UncompressChunkDone().]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  [bool]{.keywordtype} IsGzipFooterComplete()
[const]{.keyword};
:::

::: {.line}
[]{#l00246}[ 246]{.lineno} 
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  [// Have we parsed the complete gzip footer,
and does it match the]{.comment}
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  [// length and CRC checksum of the content
that we have uncompressed]{.comment}
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  [// so far?]{.comment}
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  [bool]{.keywordtype} IsGzipFooterValid()
[const]{.keyword};
:::

::: {.line}
[]{#l00251}[ 251]{.lineno} 
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [// Accessor for the uncompressed
size]{.comment}
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  uLong uncompressed\_size()[ const
]{.keyword}{ [return]{.keywordflow} uncompressed\_size\_; }
:::

::: {.line}
[]{#l00254}[ 254]{.lineno} 
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  [int]{.keywordtype} InflateInit(); [// sets
up the zlib inflate structure]{.comment}
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  [int]{.keywordtype} DeflateInit(); [// sets
up the zlib deflate structure]{.comment}
:::

::: {.line}
[]{#l00258}[ 258]{.lineno} 
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [// These init the zlib data structures for
compressing/uncompressing]{.comment}
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  [int]{.keywordtype} CompressInit(Bytef
\*dest, uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  uLong \*sourceLen);
:::

::: {.line}
[]{#l00262}[ 262]{.lineno}  [int]{.keywordtype} UncompressInit(Bytef
\*dest, uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00263}[ 263]{.lineno}  uLong \*sourceLen);
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  [// Initialization method to be called if we
hit an error while]{.comment}
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  [// uncompressing. On hitting an error, call
this method before]{.comment}
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  [// returning the error.]{.comment}
:::

::: {.line}
[]{#l00267}[ 267]{.lineno}  [void]{.keywordtype} UncompressErrorInit();
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  [// Helper functions to write gzip-specific
data]{.comment}
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  [int]{.keywordtype} WriteGzipHeader();
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  [int]{.keywordtype} WriteGzipFooter(Bytef
\*dest, uLongf destLen);
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} 
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  [// Helper function for both Compress and
CompressChunk]{.comment}
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [int]{.keywordtype} CompressChunkOrAll(Bytef
\*dest, uLongf \*destLen, [const]{.keyword} Bytef \*source,
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  uLong sourceLen, [int]{.keywordtype}
flush\_mode);
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  [int]{.keywordtype}
CompressAtMostOrAll(Bytef \*dest, uLongf \*destLen, [const]{.keyword}
Bytef \*source,
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  uLong \*sourceLen, [int]{.keywordtype}
flush\_mode);
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  [// Likewise for
UncompressAndUncompressChunk]{.comment}
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  [int]{.keywordtype}
UncompressChunkOrAll(Bytef \*dest, uLongf \*destLen, [const]{.keyword}
Bytef \*source,
:::

::: {.line}
[]{#l00280}[ 280]{.lineno}  uLong sourceLen, [int]{.keywordtype}
flush\_mode);
:::

::: {.line}
[]{#l00281}[ 281]{.lineno} 
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  [int]{.keywordtype}
UncompressAtMostOrAll(Bytef \*dest, uLongf \*destLen, [const]{.keyword}
Bytef \*source,
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  uLong \*sourceLen, [int]{.keywordtype}
flush\_mode);
:::

::: {.line}
[]{#l00284}[ 284]{.lineno} 
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [// Initialization method to be called if we
hit an error while]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [// compressing. On hitting an error, call
this method before]{.comment}
:::

::: {.line}
[]{#l00287}[ 287]{.lineno}  [// returning the error.]{.comment}
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [void]{.keywordtype} CompressErrorInit();
:::

::: {.line}
[]{#l00289}[ 289]{.lineno} 
:::

::: {.line}
[]{#l00290}[ 290]{.lineno}  [struct ]{.keyword}Settings {
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  [// compression level]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  [int]{.keywordtype} compression\_level\_;
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} 
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  [// log base 2 of the window size used in
compression]{.comment}
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  [int]{.keywordtype} window\_bits\_;
:::

::: {.line}
[]{#l00296}[ 296]{.lineno} 
:::

::: {.line}
[]{#l00297}[ 297]{.lineno}  [// specifies the amount of memory to be
used by compressor (1-9)]{.comment}
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  [int]{.keywordtype} mem\_level\_;
:::

::: {.line}
[]{#l00299}[ 299]{.lineno} 
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  [// Controls behavior of
UncompressAtMostOrAll with regards to returning]{.comment}
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  [// Z\_STREAM\_END. See comments for
SetDontHideStreamEnd.]{.comment}
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  [bool]{.keywordtype}
dont\_hide\_zstream\_end\_;
:::

::: {.line}
[]{#l00303}[ 303]{.lineno}  };
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} 
:::

::: {.line}
[]{#l00305}[ 305]{.lineno}  [// \"Current\" settings. These will be used
whenever we next configure zlib.]{.comment}
:::

::: {.line}
[]{#l00306}[ 306]{.lineno}  [// For example changing compression level
or header mode will be recorded]{.comment}
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  [// in these, but don\'t usually get applied
immediately but on next compress.]{.comment}
:::

::: {.line}
[]{#l00308}[ 308]{.lineno}  Settings settings\_;
:::

::: {.line}
[]{#l00309}[ 309]{.lineno} 
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  [// Settings last used to initialise and
configure zlib. These are needed]{.comment}
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  [// to know if the current desired
configuration in settings\_ is sufficiently]{.comment}
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [// compatible with the previous
configuration and we can just reconfigure the]{.comment}
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  [// underlying zlib objects, or have to
recreate them from scratch.]{.comment}
:::

::: {.line}
[]{#l00314}[ 314]{.lineno}  Settings init\_settings\_;
:::

::: {.line}
[]{#l00315}[ 315]{.lineno} 
:::

::: {.line}
[]{#l00316}[ 316]{.lineno}  z\_stream comp\_stream\_; [// Zlib stream
data structure]{.comment}
:::

::: {.line}
[]{#l00317}[ 317]{.lineno}  [bool]{.keywordtype} comp\_init\_; [// True
if we have initialized comp\_stream\_]{.comment}
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  z\_stream uncomp\_stream\_; [// Zlib stream
data structure]{.comment}
:::

::: {.line}
[]{#l00319}[ 319]{.lineno}  [bool]{.keywordtype} uncomp\_init\_; [//
True if we have initialized uncomp\_stream\_]{.comment}
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
:::

::: {.line}
[]{#l00321}[ 321]{.lineno}  [// These are used only in gzip compression
mode]{.comment}
:::

::: {.line}
[]{#l00322}[ 322]{.lineno}  uLong crc\_; [// stored in gzip footer,
fitting 4 bytes]{.comment}
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  uLong uncompressed\_size\_;
:::

::: {.line}
[]{#l00324}[ 324]{.lineno} 
:::

::: {.line}
[]{#l00325}[ 325]{.lineno} 
[GZipHeader](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html){.code}
\*gzip\_header\_; [// our gzip header state]{.comment}
:::

::: {.line}
[]{#l00326}[ 326]{.lineno} 
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  Byte gzip\_footer\_\[8\]; [// stored footer,
used to uncompress]{.comment}
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  [int]{.keywordtype} gzip\_footer\_bytes\_;
[// num of footer bytes read so far, or -1]{.comment}
:::

::: {.line}
[]{#l00329}[ 329]{.lineno} 
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  [// These are used only with chunked
compression.]{.comment}
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [bool]{.keywordtype} first\_chunk\_; [//
true if we need to emit headers with this chunk]{.comment}
:::

::: {.line}
[]{#l00332}[ 332]{.lineno} };
:::

::: {.line}
[]{#l00333}[ 333]{.lineno} 
:::

::: {.line}
[]{#l00334}[ 334]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00335}[ 335]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00336}[ 336]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00337}[ 337]{.lineno} 
:::

::: {.line}
[]{#l00338}[ 338]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_COMPRESSION\_GZIP\_ZLIB\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1GZipHeader_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::GZipHeader](classtensorflow_1_1serving_1_1net__http_1_1GZipHeader.html)
:::

::: {.ttdef}
**Definition:** gzip\_zlib.h:27
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ZLib_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ZLib](classtensorflow_1_1serving_1_1net__http_1_1ZLib.html)
:::

::: {.ttdef}
**Definition:** gzip\_zlib.h:94
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
