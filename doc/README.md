<a name="Pulse"></a>
## Pulse
Beats per minute (BPM) automatic detection with Web Audio API.

**Kind**: global class  

* [Pulse](#Pulse)
  * [new Pulse(options)](#new_Pulse_new)
  * [.audioContext](#Pulse#audioContext) : <code>object</code>
  * [.buffer](#Pulse#buffer) : <code>object</code>
  * [.renderedBuffer](#Pulse#renderedBuffer) : <code>object</code>
  * [.significantPeaks](#Pulse#significantPeaks) : <code>object</code>
  * [.beat](#Pulse#beat) : <code>object</code>
  * [.REQUEST_PROGRESS](#Pulse#REQUEST_PROGRESS) : <code>number</code>
  * [.REQUEST_LOAD](#Pulse#REQUEST_LOAD) : <code>number</code>
  * [.REQUEST_ERROR](#Pulse#REQUEST_ERROR) : <code>number</code>
  * [.REQUEST_ABORT](#Pulse#REQUEST_ABORT) : <code>number</code>
  * [.WEB_AUDIO_API_NOT_SUPPORTED](#Pulse#WEB_AUDIO_API_NOT_SUPPORTED) : <code>number</code>
  * [.state](#Pulse#state) : <code>number</code>
  * [.options](#Pulse#options) : <code>object</code>
  * [.getDefaultOptions()](#Pulse#getDefaultOptions) ⇒ <code>object</code>
  * [.loadBufferFromURI(uri)](#Pulse#loadBufferFromURI) ⇒ <code>boolean</code>
  * [._getChannelDataMinMax()](#Pulse#_getChannelDataMinMax) ⇒ <code>object</code>
  * [.getSignificantPeaks()](#Pulse#getSignificantPeaks) ⇒ <code>object</code>
  * [.getBeat()](#Pulse#getBeat) ⇒ <code>object</code>
  * [.getExtrapolatedPeaks()](#Pulse#getExtrapolatedPeaks) ⇒ <code>object</code>

<a name="new_Pulse_new"></a>
### new Pulse(options)

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| options | <code>object</code> |  | Options available for Pulse. |
| options.onComplete | <code>function</code> |  | Fired when Pulse has finished to compute main data: beat, significant peaks. |
| options.onRequestProgress | <code>function</code> |  | Fired when the XHR object is downloading data. |
| options.onRequestSuccess | <code>function</code> |  | Fired when the XHR object has successfully finished. |
| options.onRequestAbort | <code>function</code> |  | Fired when the XHR object has aborted. |
| options.onRequestError | <code>function</code> |  | Fired when the XHR object has an error occured. |
| [options.convertToMilliseconds] | <code>boolean</code> | <code>true</code> | If false, significant peaks are in Hertz unit. |
| [options.removeDuplicates] | <code>boolean</code> | <code>true</code> | If false, all significant peaks are computed. |

<a name="Pulse#audioContext"></a>
### pulse.audioContext : <code>object</code>
The Audio Context object.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
<a name="Pulse#buffer"></a>
### pulse.buffer : <code>object</code>
The buffer that contains audio data.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Default**: <code>null</code>  
<a name="Pulse#renderedBuffer"></a>
### pulse.renderedBuffer : <code>object</code>
The rendered buffer in the offline audio context.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Default**: <code>null</code>  
<a name="Pulse#significantPeaks"></a>
### pulse.significantPeaks : <code>object</code>
The array of significant peaks found

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Default**: <code>null</code>  
<a name="Pulse#beat"></a>
### pulse.beat : <code>object</code>
The computed beat including milliseconds and beat per minute.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Default**: <code>{ms: null, bpm: null};</code>  
<a name="Pulse#REQUEST_PROGRESS"></a>
### pulse.REQUEST_PROGRESS : <code>number</code>
State when a request is in progress.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Read only**: true  
<a name="Pulse#REQUEST_LOAD"></a>
### pulse.REQUEST_LOAD : <code>number</code>
State when a request is downloading.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Read only**: true  
<a name="Pulse#REQUEST_ERROR"></a>
### pulse.REQUEST_ERROR : <code>number</code>
State when a request has an error.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Read only**: true  
<a name="Pulse#REQUEST_ABORT"></a>
### pulse.REQUEST_ABORT : <code>number</code>
State when a request is aborted.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Read only**: true  
<a name="Pulse#WEB_AUDIO_API_NOT_SUPPORTED"></a>
### pulse.WEB_AUDIO_API_NOT_SUPPORTED : <code>number</code>
State when the browser does not support Web Audio API.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Read only**: true  
<a name="Pulse#state"></a>
### pulse.state : <code>number</code>
The state of a Pulse operation.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
<a name="Pulse#options"></a>
### pulse.options : <code>object</code>
Options available for Pulse.

**Kind**: instance property of <code>[Pulse](#Pulse)</code>  
**Default**: <code>{}</code>  
<a name="Pulse#getDefaultOptions"></a>
### pulse.getDefaultOptions() ⇒ <code>object</code>
Get the default options.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
**Returns**: <code>object</code> - Options with default values  
<a name="Pulse#loadBufferFromURI"></a>
### pulse.loadBufferFromURI(uri) ⇒ <code>boolean</code>
Load a song from an URI.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
**Returns**: <code>boolean</code> - Always true but the request event has more information.  

| Param | Type | Description |
| --- | --- | --- |
| uri | <code>string</code> | The URI of the song. |

<a name="Pulse#_getChannelDataMinMax"></a>
### pulse._getChannelDataMinMax() ⇒ <code>object</code>
Get the min/max of a channel data.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
<a name="Pulse#getSignificantPeaks"></a>
### pulse.getSignificantPeaks() ⇒ <code>object</code>
Get the significant peaks.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
<a name="Pulse#getBeat"></a>
### pulse.getBeat() ⇒ <code>object</code>
Get the beat in milliseconds and beat per minute.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
<a name="Pulse#getExtrapolatedPeaks"></a>
### pulse.getExtrapolatedPeaks() ⇒ <code>object</code>
Get the extrapolated peaks regarding the computed beat.

**Kind**: instance method of <code>[Pulse](#Pulse)</code>  
