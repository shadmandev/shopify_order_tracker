<style>.tracking-page-wrapper{text-align:center;background:#eee;padding:30px;border-radius:8px}.tracking-page-wrapper .tack-head{font-size:20px;letter-spacing:0}.tracking-page-wrapper .track-inp{display:flex;justify-content:center}.tracking-page-wrapper .track-inp input#YQNum{width:50%;border-color:var(--colorBtnPrimary);border-top-left-radius:5px;border-bottom-left-radius:5px}.tracking-page-wrapper .track-inp input[type=button]{background:var(--colorBtnPrimary);color:var(--colorBtnPrimaryText);padding:0 25px;border-color:var(--colorBtnPrimary);border-top-right-radius:5px;border-bottom-right-radius:5px;cursor:pointer}:focus-visible{outline: -webkit-focus-ring-color auto 0px;}.track-error{display:none;background:#ffd7d7;color:#9b1c1c;padding:1rem;font-size:.875rem;line-height:1.25rem;border-radius:.5rem;font-weight:600;gap:10px;width:50%;margin:10px auto}.track-error svg{width:1.25rem;height:1.25rem}</style>
<div class="tracking-page-wrapper">
<div class="tack-head">Enter your tracking number here to see your order status.</div>
<br />
<div class="track-inp"><input type="text" id="YQNum" maxlength="50" /> <input type="button" value="TRACK" onclick="doTrack()" /></div>
<div class="track-error" id="trck-error-msg"><svg aria-hidden="true" class="flex-shrink-0 inline w-5 h-5 mr-3" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd"></path></svg>Enter your order number.</div>
<div id="YQContainer"></div>
</div>
<!--Script code can be put in the bottom of the page, wait until the page is loaded then execute.-->
<script type="text/javascript" src="//www.17track.net/externalcall.js"></script>
<script type="text/javascript">// <![CDATA[
function doTrack() {
	var num = document.getElementById("YQNum").value;
	let error_msg = document.getElementById("trck-error-msg");
	if(num===""){
		error_msg.style.display = "flex";
    	return;
	}
	YQV5.trackSingle({
    	//Required, Specify the container ID of the carrier content.
    	YQ_ContainerId:"YQContainer",
    	//Optional, specify tracking result height, max height 800px, default is 560px.
    	YQ_Height:560,
    	//Optional, select carrier, default to auto identify.
    	YQ_Fc:"0",
    	//Optional, specify UI language, default language is automatically detected based on the browser settings.
    	YQ_Lang:"en",
    	//Required, specify the number needed to be tracked.
    	YQ_Num:num
	});
}
// ]]></script>
