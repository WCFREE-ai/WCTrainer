import System;
import System.Windows.Forms;
import Fiddler;


class Handlers
{

    public static RulesOption("Hide 304s")
    BindPref("fiddlerscript.rules.Hide304s")
    var m_Hide304s: boolean = false;

    // Cause Fiddler to override the Accept-Language header with one of the defined values
    public static RulesOption("Request &Japanese Content")
    var m_Japanese: boolean = false;

    // Automatic Authentication
    public static RulesOption("&Automatically Authenticate")
    BindPref("fiddlerscript.rules.AutoAuth")
    var m_AutoAuth: boolean = false;

    // Cause Fiddler to override the User-Agent header with one of the defined values
    // The page http://browserscope2.org/browse?category=selectors&ua=Mobile%20Safari is a good place to find updated versions of these
    RulesString("&User-Agents", true) 
    BindPref("fiddlerscript.ephemeral.UserAgentString")
    RulesStringValue(0,"Netscape &3", "Mozilla/3.0 (Win95; I)")
    RulesStringValue(1,"WinPhone8.1", "Mozilla/5.0 (Mobile; Windows Phone 8.1; Android 4.0; ARM; Trident/7.0; Touch; rv:11.0; IEMobile/11.0; NOKIA; Lumia 520) like iPhone OS 7_0_3 Mac OS X AppleWebKit/537 (KHTML, like Gecko) Mobile Safari/537")
    RulesStringValue(2,"&Safari5 (Win7)", "Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US) AppleWebKit/533.21.1 (KHTML, like Gecko) Version/5.0.5 Safari/533.21.1")
    RulesStringValue(3,"Safari9 (Mac)", "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11) AppleWebKit/601.1.56 (KHTML, like Gecko) Version/9.0 Safari/601.1.56")
    RulesStringValue(4,"iPad", "Mozilla/5.0 (iPad; CPU OS 8_3 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12F5027d Safari/600.1.4")
    RulesStringValue(5,"iPhone6", "Mozilla/5.0 (iPhone; CPU iPhone OS 8_3 like Mac OS X) AppleWebKit/600.1.4 (KHTML, like Gecko) Version/8.0 Mobile/12F70 Safari/600.1.4")
    RulesStringValue(6,"IE &6 (XPSP2)", "Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1; SV1)")
    RulesStringValue(7,"IE &7 (Vista)", "Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1)")
    RulesStringValue(8,"IE 8 (Win2k3 x64)", "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 5.2; WOW64; Trident/4.0)")
    RulesStringValue(9,"IE &8 (Win7)", "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Trident/4.0)")
    RulesStringValue(10,"IE 9 (Win7)", "Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0)")
    RulesStringValue(11,"IE 10 (Win8)", "Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; WOW64; Trident/6.0)")
    RulesStringValue(12,"IE 11 (Surface2)", "Mozilla/5.0 (Windows NT 6.3; ARM; Trident/7.0; Touch; rv:11.0) like Gecko")
    RulesStringValue(13,"IE 11 (Win8.1)", "Mozilla/5.0 (Windows NT 6.3; WOW64; Trident/7.0; rv:11.0) like Gecko")
    RulesStringValue(14,"Edge (Win10)", "Mozilla/5.0 (Windows NT 10.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/46.0.2486.0 Safari/537.36 Edge/13.11082")
    RulesStringValue(15,"&Opera", "Opera/9.80 (Windows NT 6.2; WOW64) Presto/2.12.388 Version/12.17")
    RulesStringValue(16,"&Firefox 3.6", "Mozilla/5.0 (Windows; U; Windows NT 6.1; en-US; rv:1.9.2.7) Gecko/20100625 Firefox/3.6.7")
    RulesStringValue(17,"&Firefox 43", "Mozilla/5.0 (Windows NT 6.3; WOW64; rv:43.0) Gecko/20100101 Firefox/43.0")
    RulesStringValue(18,"&Firefox Phone", "Mozilla/5.0 (Mobile; rv:18.0) Gecko/18.0 Firefox/18.0")
    RulesStringValue(19,"&Firefox (Mac)", "Mozilla/5.0 (Macintosh; Intel Mac OS X 10.8; rv:24.0) Gecko/20100101 Firefox/24.0")
    RulesStringValue(20,"Chrome (Win)", "Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/48.0.2564.48 Safari/537.36")
    RulesStringValue(21,"Chrome (Android)", "Mozilla/5.0 (Linux; Android 5.1.1; Nexus 5 Build/LMY48B) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/43.0.2357.78 Mobile Safari/537.36")
    RulesStringValue(22,"ChromeBook", "Mozilla/5.0 (X11; CrOS x86_64 6680.52.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2272.74 Safari/537.36")
    RulesStringValue(23,"GoogleBot Crawler", "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)")
    RulesStringValue(24,"Kindle Fire (Silk)", "Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_3; en-us; Silk/1.0.22.79_10013310) AppleWebKit/533.16 (KHTML, like Gecko) Version/5.0 Safari/533.16 Silk-Accelerated=true")
    RulesStringValue(25,"&Custom...", "%CUSTOM%")
    public static var sUA: String = null;

    // Cause Fiddler to delay HTTP traffic to simulate typical 56k modem conditions
    public static RulesOption("Simulate &Modem Speeds", "Per&formance")
    var m_SimulateModem: boolean = false;

    // Removes HTTP-caching related headers and specifies "no-cache" on requests and responses
    public static RulesOption("&Disable Caching", "Per&formance")
    var m_DisableCaching: boolean = false;

    public static RulesOption("Cache Always &Fresh", "Per&formance")
    var m_AlwaysFresh: boolean = false;
        
    // Force a manual reload of the script file.  Resets all
    // RulesOption variables to their defaults.
    public static ToolsAction("Reset Script")
    function DoManualReload() { 
        FiddlerObject.ReloadScript();
    }

    public static ContextAction("Decode Selected Sessions")
    function DoRemoveEncoding(oSessions: Session[]) {
        for (var x:int = 0; x < oSessions.Length; x++){
            oSessions[x].utilDecodeRequest();
            oSessions[x].utilDecodeResponse();
        }
        UI.actUpdateInspector(true,true);
    }

    static function OnBeforeRequest(oSession: Session) {
        
        if (oSession.url=="wc-fb-cdn7.kixeye.com/game/assets/preloader/warcommander.png"){
            oSession.utilCreateResponseAndBypassServer();
            oSession.oResponse.headers.Add("Access-Control-Allow-Origin","*");
            var file = System.IO.File.ReadAllBytes("Untitled-1.png");
            oSession.ResponseBody = file;   
        }

        if ((null != gs_ReplaceToken) && (oSession.url.indexOf(gs_ReplaceToken)>-1)) {   // Case sensitive
            oSession.url = oSession.url.Replace(gs_ReplaceToken, gs_ReplaceTokenWith); 
        }
        if ((null != gs_OverridenHost) && (oSession.host.toLowerCase() == gs_OverridenHost)) {
            oSession["x-overridehost"] = gs_OverrideHostWith; 
        }

        if ((null!=bpRequestURI) && oSession.uriContains(bpRequestURI)) {
            oSession["x-breakrequest"]="uri";
        }

        if ((null!=bpMethod) && (oSession.HTTPMethodIs(bpMethod))) {
            oSession["x-breakrequest"]="method";
        }

        if ((null!=uiBoldURI) && oSession.uriContains(uiBoldURI)) {
            oSession["ui-bold"]="QuickExec";
        }

        if (m_SimulateModem) {
            // Delay sends by 300ms per KB uploaded.
            oSession["request-trickle-delay"] = "300"; 
            // Delay receives by 150ms per KB downloaded.
            oSession["response-trickle-delay"] = "150"; 
        }

        if (m_DisableCaching) {
            oSession.oRequest.headers.Remove("If-None-Match");
            oSession.oRequest.headers.Remove("If-Modified-Since");
            oSession.oRequest["Pragma"] = "no-cache";
        }

        // User-Agent Overrides
        if (null != sUA) {
            oSession.oRequest["User-Agent"] = sUA; 
        }

        if (m_Japanese) {
            oSession.oRequest["Accept-Language"] = "ja";
        }

        if (m_AutoAuth) {
            // Automatically respond to any authentication challenges using the 
            // current Fiddler user's credentials. You can change (default)
            // to a domain\\username:password string if preferred.
            //
            // WARNING: This setting poses a security risk if remote 
            // connections are permitted!
            oSession["X-AutoAuth"] = "(default)";
        }

        if (m_AlwaysFresh && (oSession.oRequest.headers.Exists("If-Modified-Since") || oSession.oRequest.headers.Exists("If-None-Match")))
        {
            oSession.utilCreateResponseAndBypassServer();
            oSession.responseCode = 304;
            oSession["ui-backcolor"] = "Lavender";
        }
    }

    // This function is called immediately after a set of request headers has
    // been read from the client. This is typically too early to do much useful
    // work, since the body hasn't yet been read, but sometimes it may be useful.
    //
    // For instance, see 
    // http://blogs.msdn.com/b/fiddler/archive/2011/11/05/http-expect-continue-delays-transmitting-post-bodies-by-up-to-350-milliseconds.aspx
    // for one useful thing you can do with this handler.
    //
    // Note: oSession.requestBodyBytes is not available within this function!
    /*
    static function OnPeekAtRequestHeaders(oSession: Session) {
    var sProc = ("" + oSession["x-ProcessInfo"]).ToLower();
    if (!sProc.StartsWith("mylowercaseappname")) oSession["ui-hide"] = "NotMyApp";
    }
    */

    //
    // If a given session has response streaming enabled, then the OnBeforeResponse function 
    // is actually called AFTER the response was returned to the client.
    //
    // In contrast, this OnPeekAtResponseHeaders function is called before the response headers are 
    // sent to the client (and before the body is read from the server).  Hence this is an opportune time 
    // to disable streaming (oSession.bBufferResponse = true) if there is something in the response headers 
    // which suggests that tampering with the response body is necessary.
    // 
    // Note: oSession.responseBodyBytes is not available within this function!
    //
    static function OnPeekAtResponseHeaders(oSession: Session) {
        //FiddlerApplication.Log.LogFormat("Session {0}: Response header peek shows status is {1}", oSession.id, oSession.responseCode);
        if (m_DisableCaching) {
            oSession.oResponse.headers.Remove("Expires");
            oSession.oResponse["Cache-Control"] = "no-cache";
        }

        if ((bpStatus>0) && (oSession.responseCode == bpStatus)) {
            oSession["x-breakresponse"]="status";
            oSession.bBufferResponse = true;
        }
        
        if ((null!=bpResponseURI) && oSession.uriContains(bpResponseURI)) {
            oSession["x-breakresponse"]="uri";
            oSession.bBufferResponse = true;
        }

    }
	

	static function OnBeforeResponse(oSession: Session) {
		if (m_Hide304s && oSession.responseCode == 304) {
			oSession["ui-hide"] = "true";
		}
        
		if (oSession.url.Contains("https://wc-fb-vip.sjc.kixeye.com/canvas/")){
			oSession.utilReplaceInResponse('suspended','')
		}
        
		if (oSession.url=="https://www.google.com/recaptcha/api.js?onload=onloadcallback&render=explicit"){
            
			oSession.utilReplaceInResponse('gr.ready=gr.ready||function(f)','');
            
		}
        
        
		if (oSession.url.Contains("WarCommander.js")){
                       
			oSession.utilDecodeResponse();
            
			oSession.utilReplaceInResponse('{return this._hidden}','{return !1}');
			oSession.utilReplaceInResponse('{return get_costSku: function()}','{return this._costSku !1}');
			oSession.utilReplaceInResponse('e[g].get_Health()','e[g].get_MaxHealth()');
			oSession.utilReplaceInResponse('Za.FromISOFromCoords(a.x * c, a.y * c * .5)','Za.FromISOFromCoords(0, 0)');
			oSession.utilReplaceInResponse('(Wa.createPurchaseBoost(a, b.get_costSku(), b.get_costQuantity()), null, !0)','(Wa.createPurchaseBoost(a, b.get_costSku(), b.get_costQuantity()), null, !1)');
			oSession.utilReplaceInResponse('warEffortsButton.set_visible(!0)','warEffortsButton.set_visible(!1)');
            
			//Barracks
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return x._tg(a)}','tion(a){a=A.gut(a);return 29}');
            
			//Airfield
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 13}');
            
			//War Factory
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 30}');
            
			//Missile Silo
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 37}');
            
			//Merc Camp
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 74}');
            
            
			//oSession.utilReplaceInResponse('hasTrait(4):!1}','hasTrait(4):!0}');
			//oSession.utilReplaceInResponse(',onSaveErrorReceived:function(a,b){n.showErrorMessage(2181,a)}','');
			//oSession.utilReplaceInResponse(',onSaveErrorReceived:function(a,b){n.showErrorMessage(2030,a)}','');
            
			//Mines Build Free&&Fast//
			oSession.utilReplaceInResponse("a.Action(!1)}):this.Action(!0)", "a.Action(!1)}):this.Action(!0)");
			//oSession.utilReplaceInResponse('Ma.ProduceMine(d);break}}}','Ma.ProduceMine(b++);break}}};');
			oSession.utilReplaceInResponse('Ma.ProduceMine(this._mineSlot))},','Ma.ProduceMine(1),Ma.ProduceMine(0),Ma.ProduceMine(2),Ma.ProduceMine(3),Ma.ProduceMine(4),Ma.ProduceMine(5),Ma.ProduceMine(6),Ma.ProduceMine(7),Ma.ProduceMine(8),Ma.ProduceMine(9),Ma.ProduceMine(10),Ma.ProduceMine(11),Ma.ProduceMine(12),Ma.ProduceMine(13),Ma.ProduceMine(14),Ma.ProduceMine(15),Ma.ProduceMine(16),Ma.ProduceMine(17),Ma.ProduceMine(18))},');
            
			//Cheap reload
			//oSession.utilReplaceInResponse('return null!=a?this.getAmmoToReload()*a.get_reloadTime()|0:0','return 305')
            
			//Unstealth Units//
			oSession.utilReplaceInResponse(';if(this.get_mine()||F.IsAdvanceScouting())a*=.6;0<this._f',';if(this.get_mine()||F.IsSyncBattleDefender()||F.IsBattle()||F.IsPlatoon()||F.IsAdvanceScouting())a*=.6;0<this._');
            
			//sector breach
			oSession.utilReplaceInResponse(':0==this._platoon.get_properties().get_canDamagedUnitsExit()&&this._platoon.hasDamagedUnits()&&!n.get_AllowDamagedPlatoonManagement()?Db.DisplayMessage(l.getString("widget_title__repair_units_before_disband"),l.getString("widget_body__repair_units_before_disband")):',':');
			oSession.utilReplaceInResponse(':0==this._platoon.get_properties().get_canDamagedUnitsExit()&&this._platoon.hasDamagedUnits()&&!q.get_AllowDamagedPlatoonManagement()?Ab.DisplayMessage(m.getString("widget_title__repair_units_before_disband"),m.getString("widget_body__repair_units_before_disband")):',':');
			oSession.utilReplaceInResponse(':0==this._platoon.get_properties().get_canDamagedUnitsExit()&&this._platoon.hasDamagedUnits()&&!q.get_AllowDamagedPlatoonManagement()?Db.DisplayMessage(l.getString("widget_title__repair_units_before_disband"),l.getString("widget_body__repair_units_before_disband")):',':');
            
            
			//Missile Cooldown//
			//oSession.utilReplaceInResponse(',onSaveErrorReceived:function(a,b){m.showErrorMessage(2191,a)}','');
          
			//afk
			//oSession.utilReplaceInResponse('var Db=function(){};k.POPUPS=Db;Db.__name__="POPUPS";Db.showAFKPopup=function(){m.ExitFullscreen();W.HideAll();','var Db=function(){};k.POPUPS=Db;Db.__name__="POPUPS";Db.showAFKPopup=function(){return;m.ExitFullscreen();W.HideAll();');
            
            
			//oSession.utilReplaceInResponse('&&z.set_Credits(va.ensureInt(a.credits));null!=a.resources&&','&&z.set_Credits(va.ensureInt(q.string(59762)));null!=a.resources&&');
            
			//level Bases Change XP//
			//oSession.utilReplaceInResponse('isTechItemEventLocked(b)','hasUnlockedTechItem(a)'); // level 15
			//oSession.utilReplaceInResponse('z.PointsAdd(a)','z.PointsAdd(2280268261)'); // level 43
			//oSession.utilReplaceInResponse('z.PointsAdd(a)','z.PointsAdd(99999999999999999999999)'); // level 53

			//New User and Fast Relocate
			//oSession.utilReplaceInResponse('er=function(){return ha.playerInfo.baseAge>=U.get_newUserRelocationRequiredAgeSec()?','er=function(){return 0};');
			//oSession.utilReplaceInResponse('er=function(){return ha.playerInfo.baseAge>=P.get_newUserRelocationRequiredAgeSec()?','er=function(){return 0};');
			//oSession.utilReplaceInResponse('er=function(){return fa.playerInfo.baseAge>=R.get_newUserRelocationRequiredAgeSec()?','er=function(){return 0};');
			//oSession.utilReplaceInResponse('ha.playerInfo.timePlayed<U.get_newUserRelocationRequiredPlaytimeSec():!0};','');
			//oSession.utilReplaceInResponse('{return ha.playerInfo.baseAge>=P.get_newUserRelocationRequiredAgeSec()?ha.playerInfo.timePlayed<P.get_newUserRelocationRequiredPlaytimeSec():!0};','');
			oSession.utilReplaceInResponse('break;case 2106:"near_friend"==wb._relocateType?Ab.DisplayMessage(m.getString("relocatebase_title__no_room"),m.getString("relocatebase_body__friend_has_no_room",{name:wb._relocateToName})):"sector"==wb._relocateType?Ab.DisplayMessage(m.getString("relocatebase_title__no_room"),m.getString("relocatebase_body__sector_has_no_room",{sector:wb._relocateToSector})):Ab.DisplayMessage(m.getString("relocatebase_title__no_room"),m.getString("relocatebase_body__common_no_room"));','');
			oSession.utilReplaceInResponse('enabled(!1)','enabled(!0)');
			//oSession.utilReplaceInResponse('visible(!1)','visible(!0)');
			oSession.utilReplaceInResponse('get_controller().requestEntities();else wb.onError(a.errorCode)};wb.onAnimHalfway=function()','get_controller().requestEntities();wb.onAnimHalfway=function()');
			oSession.utilReplaceInResponse('ze.Show(l.getString("relocatebase__relocating_base"));','');
			//oSession.utilReplaceInResponse(',{baseage:n.ToTime(ha.playerInfo.baseAge),timeplayed:n.ToTime(ha.playerInfo.timePlayed),requiredage:n.ToTime(P.get_newUserRelocationRequiredAgeSec()),requiredtime:n.ToTime(P.get_newUserRelocationRequiredPlaytimeSec())})):F.IsHomeBase()?this.relocate():(F.get_signalStateChanged().add(h(this,this.stateChanged)),F.goHome()):Db.DisplayWorldmapDown())}}','')

			//oSession.utilReplaceInResponse('&&z.set_Credits(va.ensureInt(a.credits));null!=a.resources&&','&&z.set_Credits(va.ensureInt(q.string(12954)));null!=a.resources&&');
                   
                             
			//Unstealth Units
			//oSession.utilReplaceInResponse(';if(this.get_mine()||C.IsAdvanceScouting())a*=.6;0<this._f',';if(this.get_mine()||C.IsSyncBattleDefender()||C.IsBattle()||C.IsPlatoon()||C.IsAdvanceScouting())a*=.6;0<this._');
            
			//Thor Goodies
			//oSession.utilReplaceInResponse('c=a._cost','d=0');
			//oSession.utilReplaceInResponse('d=a._cost','d=0');
			//oSession.utilReplaceInResponse('if(Nf.get_hasQueuedCancellations())W.Show(new Ib(l.getString("popup__unit_queue_cancel_title"),l.getString("popup__unit_queue_cancel_body")));else','');
			//oSession.utilReplaceInResponse('if(Nf.get_hasQueuedCancellations())W.Show(new Ib(l.getString("popup__unit_queue_cancel_title"),l.getString("popup__unit_queue_cancel_body")));else','');
			//oSession.utilReplaceInResponse('e&&(c=c/n|0,y.Purchase(a.get_storeCode(),c,a.GetAnalyticsData()))','');
			//oSession.utilReplaceInResponse('e&&(c=c/d|0,z.Purchase(a.get_storeCode(),c,a.GetAnalyticsData()))','');
			//oSession.utilReplaceInResponse(',onSaveErrorReceived:function(a,b){m.showErrorMessage(2181,a)}','');
			//oSession.utilReplaceInResponse('onSuccess:function(a){if(0==a.error)this.SaveSuccess(a);else{var','onSuccess:function(a){if(0>=0)this.SaveSuccess(a);else{var');

			
			//Deploy Toons from deposits 
			// oSession.utilReplaceInResponse('a=!1;0<this.getActionsByType(8)','a=!0;0<this.getActionsByType(8)');
			// oSession.utilReplaceInResponse('a.get_productionCostR1(),a.get_productionCostR2(),a.get_productionCostR3()','0,0,0');
            
			//Deploy toons while getting attack    .hasPendingPurchase()||!y.canSaveBase()
			//oSession.utilReplaceInResponse('4==Z.get_MapView().getHexMapCell(ha.playerInfo.get_homeBa','0==Z.get_MapView().getHexMapCell(ha.playerInfo.get_homeBa');
            
			//Add A attack button and remove the error
			oSession.utilReplaceInResponse('k;case 83:this._attackOrScoutRequested||null==this.get_mousedOverTile()||this.performScout(a.shiftKey)}}','k;case 83:this._attackOrScoutRequested||null==this.get_mousedOverTile()||this.performScout(a.shiftKey);break;case 65:null==this.get_mousedOverTile()||this.confirmAttack()}}');
			oSession.utilReplaceInResponse('c=l.getString("worldmap__cannot_attack");','');
			oSession.utilReplaceInResponse('d=l.getString("worldmap__you_cannot_attack_target",{target:f});','');
            
			//Add buttons - Bldgmerc produce and ,OpenMissileSilo:function(a){a=y.getUniqueBuildingForType(37);1==a.get_repairing()||a.
			//oSession.utilReplaceInResponse('IsBattleStarted()?(this._leaveButton=this._widget.AddButton(l.getString("ui_button__leave"),h(this,this.LeaveBattle)),','IsBattleStarted()?(this._leaveButton=this._widget.AddButton(l.getString("Mercs"),h(this,this.MercCampOpen)),this._leaveButton=this._widget.AddButton(l.getString("Missiles"),h(this,this.missilesOpen)),this._leaveButton=this._widget.AddButton(l.getString("ui_button__leave"),h(this,this.LeaveBattle)),');
			//oSession.utilReplaceInResponse('RetreatBattle:function(a){null!=this._endButton&&(this._endButton.','MercCampOpen:function(a){W.Show(new My)},missilesOpen:function(a){W.Show(new fq(4))},RetreatBattle:function(a){null!=this._endButton&&(this._endButton.');
            
			//Boosts
			oSession.utilReplaceInResponse('{return this._hidden}','{return !1}');
            
            
			//Air Spawn Top Right
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','0.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|5};');
            
			//Air Spawn Right
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|0};');
            
			//Air Spawn Bottom Right
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|1};');
            
			//Air Spawn Bottom Left
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|2};');
            
			//Air Spawn Left
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|3};');
            
			//Air Spawn Top Left
			//oSession.utilReplaceInResponse('O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(b)|0};','O.calculateAirAttackDirection=function(a,b){a=new f(a.x,a.y);b=new f(b.x,b.y);0==b.y%2&&(b.x+=.5);0==a.y%2&&(a.x+=.5);b=Math.atan2(a.y-b.y,a.x-b.x);return $d.get_instance().getBaseInfo().getAirAttackDir(a)|4};');
            
			//Barracks
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 29}');
            
			//Airfield
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 13}');
            
			//War Factory
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 30}');
            
			//Missile Silo
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 37}');
            
			//Merc Camp
			//oSession.utilReplaceInResponse('tion(a){a=A.gut(a);return z._tg(a)}','tion(a){a=A.gut(a);return 74}');
            
            
			//Enable leave button without having toon deployed
			//oSession.utilReplaceInResponse('a=!1;for(var b=0,c=A._units;b<c.length;','a=!0;for(var b=0,c=A._units;b<c.length;');

			//multimove
			oSession.utilReplaceInResponse('return Object.prototype.hasOwnProperty.call(R._flags,"building_multimove")?0!=v.field(R._flags,"building_multimove"):!1};R.get_laserShowChance=function(){return','return true;Object.prototype.hasOwnProperty.call(R._flags,"building_multimove")?0!=v.field(R._flags,"building_multimove"):!1};R.get_laserShowChance=function(){return');
			oSession.utilReplaceInResponse('return Object.prototype.hasOwnProperty.call(S._flags,"building_multimove")?0!=v.field(S._flags,"building_multimove"):!1};S.get_laserShowChance=function(){return','return true;Object.prototype.hasOwnProperty.call(S._flags,"building_multimove")?0!=v.field(S._flags,"building_multimove"):!1};S.get_laserShowChance=function(){return');
			oSession.utilReplaceInResponse('return Object.prototype.hasOwnProperty.call(P._flags,"building_multimove")?0!=v.field(P._flags,"building_multimove"):!1};P.get_laserShowChance=function(){return','return true;Object.prototype.hasOwnProperty.call(P._flags,"building_multimove")?0!=v.field(P._flags,"building_multimove"):!1};P.get_laserShowChance=function(){return');
			oSession.utilReplaceInResponse('P.get_buildingMultimove=function(){return O','P.get_buildingMultimove=function(){return true;O');
            
			//afk
			oSession.utilReplaceInResponse('var Db=function(){};k.POPUPS=Db;Db.__name__="POPUPS";Db.showAFKPopup=function(){m.ExitFullscreen();W.HideAll();','var Db=function(){};k.POPUPS=Db;Db.__name__="POPUPS";Db.showAFKPopup=function(){return;m.ExitFullscreen();W.HideAll();');
            
			//Retreat platoon inhit
			//oSession.utilReplaceInResponse('.canRetreatGround=function(){return','.canRetreatGround=function(){return true;');
            
			//bookmarks
			//oSession.utilReplaceInResponse('if(50<=Pb._bookmarks.length)Db.DisplayMessage(l.getString("worldmap_bookmarks__cannot_add"','if(5000<=Pb._bookmarks.length)Db.DisplayMessage(l.getString("worldmap_bookmarks__cannot_add"'); 
            
			// Mines
			oSession.utilReplaceInResponse('La.ProduceMine(this._mineSlot))},','La.ProduceMine(1),La.ProduceMine(0),La.ProduceMine(2),La.ProduceMine(3),La.ProduceMine(4),La.ProduceMine(5),La.ProduceMine(6),La.ProduceMine(7),La.ProduceMine(8),La.ProduceMine(9),La.ProduceMine(10),La.ProduceMine(11),La.ProduceMine(12),La.ProduceMine(13),La.ProduceMine(14),La.ProduceMine(15),La.ProduceMine(16),La.ProduceMine(17),La.ProduceMine(18))},');
			oSession.utilReplaceInResponse('Ma.ProduceMine(this._mineSlot))},','Ma.ProduceMine(1),Ma.ProduceMine(0),Ma.ProduceMine(2),Ma.ProduceMine(3),Ma.ProduceMine(4),Ma.ProduceMine(5),Ma.ProduceMine(6),Ma.ProduceMine(7),Ma.ProduceMine(8),Ma.ProduceMine(9),Ma.ProduceMine(10),Ma.ProduceMine(11),Ma.ProduceMine(12),Ma.ProduceMine(13),Ma.ProduceMine(14),Ma.ProduceMine(15),Ma.ProduceMine(16),Ma.ProduceMine(17),Ma.ProduceMine(18))},');
			//oSession.utilReplaceInResponse('StartClick:function(){this.Hide();this._cbStart()}','StartClick:function(){this.Hide();Ja.ProduceMine(1),Ja.ProduceMine(0),Ja.ProduceMine(2),Ja.ProduceMine(3),Ja.ProduceMine(4),Ja.ProduceMine(5),Ja.ProduceMine(6),Ja.ProduceMine(7),Ja.ProduceMine(8),Ja.ProduceMine(9),Ja.ProduceMine(10),Ja.ProduceMine(11),Ja.ProduceMine(12),Ja.ProduceMine(13),Ja.ProduceMine(14),Ja.ProduceMine(15),Ja.ProduceMine(16),Ja.ProduceMine(17),Ja.ProduceMine(18),this._cbStart()}');
			oSession.utilReplaceInResponse('{a=1200;null==a&&(a=0);var','{a=1;null==a&&(a=0);var');

			//1
			//oSession.utilReplaceInResponse('visible(!1);','visible(!0);');
			//oSession.utilReplaceInResponse('fully_promoted");this._costs.set_Enabled(!0);this._costResources.set_visible(!1);','fully_promoted");this._costs.set_Enabled(!0);this._costResources.set_visible(!0);');
            
            
			//Add hotkeys
			//oSession.utilReplaceInResponse('case 68:L.standGround();','case 68:L.standGround();break;case 80:W.Show(new bm);break;case 77:W.Show(new Ny);break;case 78:W.Show(new fq(4));break;');
			//oSession.utilReplaceInResponse('||!y.canSaveBase()','');
			//oSession.utilReplaceInResponse('||!z.canSaveBase()','');

			//Air Swap
			//oSession.utilReplaceInResponse('else if(1==this._platoon.get_isAircraftPlatoon()&&this._platoon.isInBattle())e=16732497,c=-1,d=4;','');
			//oSession.utilReplaceInResponse('&&1==this._platoon.get_isAircraftPlatoon()','&&57==this._platoon.get_isAircraftPlatoon()');
			//oSession.utilReplaceInResponse('&&1==pa.instance.get_IsOwnerAttackerInActiveBattles()','&&57==pa.instance.get_IsOwnerAttackerInActiveBattles()');
            
			//Scout -> Advanced Scout
			//oSession.utilReplaceInResponse('this.getScoutingStateFromEvent(a);','14;');
            
			//Cheap reload
			//oSession.utilReplaceInResponse('return null!=a?this.getAmmoToReload()*a.get_reloadTime()|0:0','return 305');
            
			//Live Airspawn change
			//oSession.utilReplaceInResponse('Uk.addCallback("showAttackLog",function(){m.showAttackLog()}),','Uk.addCallback("showAttackLog",function(){m.showAttackLog()}),Uk.addCallback("right1",function(){O._airAttackDir=0}),Uk.addCallback("righttop",function(){O._airAttackDir=5}),Uk.addCallback("rightbottom",function(){O._airAttackDir=1}),Uk.addCallback("left1",function(){O._airAttackDir=3}),Uk.addCallback("lefttop",function(){O._airAttackDir=4}),Uk.addCallback("leftbottom",function(){O._airAttackDir=2}),');
            
			//Deploy button muffled
			//oSession.utilReplaceInResponse('this,this.Deploy','this,this.finishInstantly');
			//oSession.utilReplaceInResponse('Deploy:function(){if(0>','finishInstantly:function(){this.Save();this.repairInstantConfirmation(!0)},finish:function(a){null==a&&(a=!1);var b=h(this,this.repairConfirmation);a&&(b=h(this,this.repairInstantConfirmation));var c=Qb.GetPlatoonRepairCost(this._platoon),d=c.get_time(),e=c.get_creditsNumber();c=l.getString("popup_title__speed_up_repairing");var g=l.getString("popup_body__finish_repairing_platoon",{time:m.ToTime(d,0,!1)});if(0==e)W.Show(new Ib(l.getString("popup_button__finish_now"),l.getString("popup_body__finish_for_free"),!0,l.getString("popup_button__finish_now"),b));else{a&&(c=l.getString("popup_button__finish_now"),g=l.getString("popup_body__instant_repair_platoon",{time:m.ToTime(d,0,!1)}));var f=this.getRepairMultiplier(!1),k=hj.getRepairModifierFromFlags(),n=Math.ceil(e);if(1!=f||1!=k){d=1!=k&&0==T.get_repairReductionAffectsTime();f=Math.min(f,k);e=Math.ceil(1/f*e);if(1==T.get_repairReductionAffectsTime()&&!a){a=m.ONE_HUNDRED;k=a.x^a.s;var t=(a.n^a.s)-2*a.s;k==t?a=k:(V.BadNum(a,k,t),a=0);k=m.ONE_HUNDRED;t=k.x^k.s;var r=(k.n^k.s)-2*k.s;t==r?k=t:(V.BadNum(k,t,r),k=0);f=q.parseInt(q.string(a-q.parseInt(q.string(f*k))));g+="<br>"+l.getString("popup_body__platoon_reduction",{percent:null==f?"null":""+f})}b=new Ai(c,g,l.getString("popup_button__finish_now"),n,b,null,null,!0,d?4:0);d&&b.ShowSalePrice(e)}else b=new Ai(c,g,l.getString("popup_button__finish_now"),n,b);W.Show(b)}},getRepairMultiplier:function(a,b){null==b&&(b=!0);null==a&&(a=!0);if(null==this._platoon)return 1;var c=Qb.getRepairQueueFromPlatoon(this._platoon);c=null!=c?c.get_repairMultiplier():1;a&&(c=Math.min(hj.getRepairModifierFromFlags(b),c));return c},repairConfirmation:function(){var a=Qb.GetPlatoonRepairCost(this._platoon);wa.Purchase(Ta.CreateRepairPlatoon(a,this._platoon.get_ID(),!1))},repairInstantConfirmation:function(){var a=Qb.GetPlatoonRepairCost(this._platoon);wa.Purchase(Wa.CreateRepairPlatoon(a,this._platoon.get_ID(),!1))},cancel:function(){if(1!=this.getRepairMultiplier()){var a=l.getString("widget_title__cancel_repair_question"),b=l.getString("widget_body__cancel_reduced_repair_confirm");a=new Ib(a,b,!0,l.getString("Stop Repairs"),h(this,this.cancelConfirmation));a.AddButton(l.getString("common_button__cancel"),null,1);a.set_ID(41);W.Show(a,!0)}else this.cancelConfirmation()},Deploy:function(){if(0>');
           
			//Reset Cooldown
			//oSession.utilReplaceInResponse('Kc.canUseService(this._wcDataStorageService,"resetCooldown")&&this._wcDataStorageService.resetCooldown(a)','return !0');
            
			//oSession.utilReplaceInResponse('move_error_entity_not_found")}Db.DisplayMessage(b,c)','move_error_entity_not_found")}');
         
			//Trophy HIDE ENEMY//
			oSession.utilReplaceInResponse('Da.prototype.ImageCallback.call(this,a,b)',''); 

            
		}

		if (oSession.url.Contains("prod-kx-vip.sjc.kixeye.com/assets/script/cc-framework.")){
			oSession.utilDecodeResponse();
			var replace = " right1: function(view) { if(!this.inited) return false; return this.sendToSwf('right1'); }, righttop: function(view) { if(!this.inited) return false; return this.sendToSwf('righttop'); }, rightbottom: function(view) { if(!this.inited) return false; return this.sendToSwf('rightbottom'); }, left1: function(view) { if(!this.inited) return false; return this.sendToSwf('left1'); }, lefttop: function(view) { if(!this.inited) return false; return this.sendToSwf('lefttop'); }, leftbottom: function(view) { if(!this.inited) return false; return this.sendToSwf('leftbottom'); },showAttackLog: function(view)";
			oSession.utilReplaceInResponse('showAttackLog: function(view)',replace);
            
		}
        
		if (oSession.url=="prod-fb-vip.sjc.kixeye.com/canvas/topuppopup"){
			oSession.utilDecodeResponse();
			oSession.utilReplaceInResponse('paymentHelper(340','giftGoldHelper(340');
			oSession.utilReplaceInResponse('paymentHelper(360','giftGoldHelper(360');
            
            
		}
        
		if (oSession.url=="prod-kx-vip.sjc.kixeye.com/canvas/topuppopup"){
			oSession.utilDecodeResponse();
			//oSession.utilReplaceInResponse('paymentHelper(37','paymentHelper(36');
            
        
		}    
            
		if (oSession.url=="prod-fb-vip.sjc.kixeye.com/canvas/giftgoldconfirm"){
			oSession.utilDecodeResponse();
			oSession.utilReplaceInResponse('34','36');
            
		}    
            
       
	}

/*
    // This function executes just before Fiddler returns an error that it has 
    // itself generated (e.g. "DNS Lookup failure") to the client application.
    // These responses will not run through the OnBeforeResponse function above.
    static function OnReturningError(oSession: Session) {
    }
*/
/*
    // This function executes after Fiddler finishes processing a Session, regardless
    // of whether it succeeded or failed. Note that this typically runs AFTER the last
    // update of the Web Sessions UI listitem, so you must manually refresh the Session's
    // UI if you intend to change it.
    static function OnDone(oSession: Session) {
    }
*/

    /*
    static function OnBoot() {
        MessageBox.Show("Fiddler has finished booting");
        System.Diagnostics.Process.Start("iexplore.exe");

        UI.ActivateRequestInspector("HEADERS");
        UI.ActivateResponseInspector("HEADERS");
    }
    */

    /*
    static function OnBeforeShutdown(): Boolean {
        // Return false to cancel shutdown.
        return ((0 == FiddlerApplication.UI.lvSessions.TotalItemCount()) ||
                (DialogResult.Yes == MessageBox.Show("Allow Fiddler to exit?", "Go Bye-bye?",
                 MessageBoxButtons.YesNo, MessageBoxIcon.Question, MessageBoxDefaultButton.Button2)));
    }
    */

    /*
    static function OnShutdown() {
            MessageBox.Show("Fiddler has shutdown");
    }
    */

    /*
    static function OnAttach() {
        MessageBox.Show("Fiddler is now the system proxy");
    }
    */

    /*
    static function OnDetach() {
        MessageBox.Show("Fiddler is no longer the system proxy");
    }
    */

    // The Main() function runs everytime your FiddlerScript compiles
	static function Main() {
		var today: Date = new Date();
		FiddlerObject.StatusText = " CustomRules.js was loaded at: " + today;

		// Uncomment to add a "Server" column containing the response "Server" header, if present
		// UI.lvSessions.AddBoundColumn("Server", 50, "@response.server");

		// Uncomment to add a global hotkey (Win+G) that invokes the ExecAction method below...
		// UI.RegisterCustomHotkey(HotkeyModifiers.Windows, Keys.G, "screenshot"); 
	}

	// These static variables are used for simple breakpointing & other QuickExec rules 
	BindPref("fiddlerscript.ephemeral.bpRequestURI")
	public static var bpRequestURI:String = null;

	BindPref("fiddlerscript.ephemeral.bpResponseURI")
	public static var bpResponseURI:String = null;

	BindPref("fiddlerscript.ephemeral.bpMethod")
	public static var bpMethod: String = null;

	static var bpStatus:int = -1;
	static var uiBoldURI: String = null;
	static var gs_ReplaceToken: String = null;
	static var gs_ReplaceTokenWith: String = null;
	static var gs_OverridenHost: String = null;
	static var gs_OverrideHostWith: String = null;

	// The OnExecAction function is called by either the QuickExec box in the Fiddler window,
	// or by the ExecAction.exe command line utility.
	static function OnExecAction(sParams: String[]): Boolean {

		FiddlerObject.StatusText = "ExecAction: " + sParams[0];

		var sAction = sParams[0].toLowerCase();
		switch (sAction) {
			case "bold":
				if (sParams.Length<2) {uiBoldURI=null; FiddlerObject.StatusText="Bolding cleared"; return false;}
				uiBoldURI = sParams[1]; FiddlerObject.StatusText="Bolding requests for " + uiBoldURI;
				return true;
			case "bp":
				FiddlerObject.alert("bpu = breakpoint request for uri\nbpm = breakpoint request method\nbps=breakpoint response status\nbpafter = breakpoint response for URI");
				return true;
			case "bps":
				if (sParams.Length<2) {bpStatus=-1; FiddlerObject.StatusText="Response Status breakpoint cleared"; return false;}
				bpStatus = parseInt(sParams[1]); FiddlerObject.StatusText="Response status breakpoint for " + sParams[1];
				return true;
			case "bpv":
			case "bpm":
				if (sParams.Length<2) {bpMethod=null; FiddlerObject.StatusText="Request Method breakpoint cleared"; return false;}
				bpMethod = sParams[1].toUpperCase(); FiddlerObject.StatusText="Request Method breakpoint for " + bpMethod;
				return true;
			case "bpu":
				if (sParams.Length<2) {bpRequestURI=null; FiddlerObject.StatusText="RequestURI breakpoint cleared"; return false;}
				bpRequestURI = sParams[1]; 
				FiddlerObject.StatusText="RequestURI breakpoint for "+sParams[1];
				return true;
			case "bpa":
			case "bpafter":
				if (sParams.Length<2) {bpResponseURI=null; FiddlerObject.StatusText="ResponseURI breakpoint cleared"; return false;}
				bpResponseURI = sParams[1]; 
				FiddlerObject.StatusText="ResponseURI breakpoint for "+sParams[1];
				return true;
			case "overridehost":
				if (sParams.Length<3) {gs_OverridenHost=null; FiddlerObject.StatusText="Host Override cleared"; return false;}
				gs_OverridenHost = sParams[1].toLowerCase();
				gs_OverrideHostWith = sParams[2];
				FiddlerObject.StatusText="Connecting to [" + gs_OverrideHostWith + "] for requests to [" + gs_OverridenHost + "]";
				return true;
			case "urlreplace":
				if (sParams.Length<3) {gs_ReplaceToken=null; FiddlerObject.StatusText="URL Replacement cleared"; return false;}
				gs_ReplaceToken = sParams[1];
				gs_ReplaceTokenWith = sParams[2].Replace(" ", "%20");  // Simple helper
				FiddlerObject.StatusText="Replacing [" + gs_ReplaceToken + "] in URIs with [" + gs_ReplaceTokenWith + "]";
				return true;
			case "allbut":
			case "keeponly":
				if (sParams.Length<2) { FiddlerObject.StatusText="Please specify Content-Type to retain during wipe."; return false;}
				UI.actSelectSessionsWithResponseHeaderValue("Content-Type", sParams[1]);
				UI.actRemoveUnselectedSessions();
				UI.lvSessions.SelectedItems.Clear();
				FiddlerObject.StatusText="Removed all but Content-Type: " + sParams[1];
				return true;
			case "stop":
				UI.actDetachProxy();
				return true;
			case "start":
				UI.actAttachProxy();
				return true;
			case "cls":
			case "clear":
				UI.actRemoveAllSessions();
				return true;
			case "g":
			case "go":
				UI.actResumeAllSessions();
				return true;
			case "goto":
				if (sParams.Length != 2) return false;
				Utilities.LaunchHyperlink("http://www.google.com/search?hl=en&btnI=I%27m+Feeling+Lucky&q=" + Utilities.UrlEncode(sParams[1]));
				return true;
			case "help":
				Utilities.LaunchHyperlink("http://fiddler2.com/r/?quickexec");
				return true;
			case "hide":
				UI.actMinimizeToTray();
				return true;
			case "log":
				FiddlerApplication.Log.LogString((sParams.Length<2) ? "User couldn't think of anything to say..." : sParams[1]);
				return true;
			case "nuke":
				UI.actClearWinINETCache();
				UI.actClearWinINETCookies(); 
				return true;
			case "screenshot":
				UI.actCaptureScreenshot(false);
				return true;
			case "show":
				UI.actRestoreWindow();
				return true;
			case "tail":
				if (sParams.Length<2) { FiddlerObject.StatusText="Please specify # of sessions to trim the session list to."; return false;}
				UI.TrimSessionList(int.Parse(sParams[1]));
				return true;
			case "quit":
				UI.actExit();
				return true;
			case "dump":
				UI.actSelectAll();
				UI.actSaveSessionsToZip(CONFIG.GetPath("Captures") + "dump.saz");
				UI.actRemoveAllSessions();
				FiddlerObject.StatusText = "Dumped all sessions to " + CONFIG.GetPath("Captures") + "dump.saz";
				return true;

			default:
				if (sAction.StartsWith("http") || sAction.StartsWith("www.")) {
					System.Diagnostics.Process.Start(sParams[0]);
					return true;
				}
				else
				{
					FiddlerObject.StatusText = "Requested ExecAction: '" + sAction + "' not found. Type HELP to learn more.";
					return false;
				}
		}
	}
}
