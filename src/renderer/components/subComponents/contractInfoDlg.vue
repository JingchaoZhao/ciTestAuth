<template>
    <div>
    	<el-dialog :modal-append-to-body="false"  :show-close="false" :close-on-press-escape="false"  class="approDlgClass" v-model="isDlgVisable" >
    		<div class="moduleTitle">
                <span style="line-height: 64px;padding-left: 20px;" class="moduleName">个人消费借款合同 </span>
                <div class="timeAndDownload">
                    <div class="timeLoad">
                        <div class="iconTime"></div> 2017-06-13 11:47:04
                    </div>
                    <div class="btnModuleDownload" @click="download"></div>
                </div>
            </div>
            <div id="personContract" style=" padding: 20px 40px; text-align: left;">
            <p class="articleTitle">个人消费借款合同</p> 
<p v-if="currentContract">合同编号：{{currentContract.contractNo}}</p>
<br>
<p>特别提醒：贷款人与其合作金融机构（如有，以下统称为“贷款人”）将为您（亦称“用户”、“本人”）提供本合同项下的人民币贷款服务。具体借款信息以本合同项下借款借据所载信息为准。借款借据是本合同组成部分之一，具有同等的法律效力。您在此确认并同意您与借款借据上所载的贷款人形成本合同项下的借款关系，受本合同约束。</p> 
<br>
<p>
为了保障您的合法权益，您应当阅读并遵守“借款合同”（以下简称“本合同”），请您务必审慎阅读、充分理解各条款内容，特别是免除或者限制责任的条款。 </p>
<br>
<p>除非您已阅读并接受本合同所有条款，否则您无权使用借款服务。您的使用、登录等行为即视为您已阅读并同意接受本合同的约束,本合同即时生效。 </p>
<br>
<p>本合同由您和贷款人共同签署。 </p>

<br><br>
<p class="subTitle">贷款基本信息</p>
<p>出借人：惠分期   </p>      
<p>身份证号码：610103197807282425</p>

<br><br><br><br>
<div>
    <p v-if="currentContract">借 款 人：{{currentContract.realName}}</p>
    <p>身份证号码：{{currentContract.credentialNo}}</p>
    <p>贷款金额：{{currentContract.loanAmount | amount2}}元</p>
    <p>贷款期限：{{currentContract.loanPeriod}}个月</p>
    <p>合同签署日期：{{currentContract.createTime | dateYYMMDD}}</p>
    <p>合同签订地及履行地：上海市  </p>
</div>

 <br><br><br><br>

<p class="subTitle">第二条、名词释义 </p>
<p>2.1 公寓企业：指与贷款人合作，并与您签订租房合同、向您出租公寓的企业。 </p>
<p>2.2 线上渠道：上海橡楠网络科技有限公司旗下公寓租房信息服务平台蜂鸟屋（以下简称“蜂鸟屋”），包括但不限于 APP、微信公众号和网站等。 </p>
<p>2.3 还款日：自贷款生效的次月起，至贷款结清前的每月账单日为每期的还款日。 </p>
<p>2.4 还款账户：指您申请、使用本贷款服务，提供给贷款人用于还款的在银行开立的账户。</p> 
<p>2.5 代扣还款：指为清偿本合同项下借款、违约金及相关费用而由您不可撤销且无条件同意并授权贷款人向您还款账户的开户行发送代扣指令，直接从还款账户划扣相应款项。 </p>
<p>2.6 账单：指自分期业务办理成功起，所生成的在还款日具体应支付的金额的账务详情。</p>
<br><br><p class="subTitle">第三条、申请及信息授权 </p>
<p>3.1 您应妥善保管您的常用电脑及手机设备（含手机号码）、公寓企业及蜂鸟屋的注册 ID、密码、手机校验码等信息，并确保不向任何人泄露您以上信息。因帐号、密码泄露所导致的损失，由您自行承担。您发现有他人冒用或盗用您的帐号及密码申请本贷款业务的，您应立即以有效方式通知贷款人，要求贷款人暂停本服务。同时，您理解贷款人对您的请求采取行动需要合理期限，在此之前，贷款人对已执行的指令及(或)所导致的您的损失不承担任何责任。 
</p><p>3.2 您保证向贷款人及蜂鸟屋平台提供的所有申请信息真实、准确、完整、合法、有效。 
</p><p>3.3 您授权贷款人向有关机构或单位（包括但不限于中国人民银行个人信用信息基础数据库、征信机构、公安机关、公积金、社保、税务、民政等）查询贷款人认为与您借款申请相关的信息，贷款人可以向中国人民银行金融信用信息基础数据库、其他依法设立的征信机构、关联公司提供您使用本服务所必要的个人身份信息及信用信息（包括不良信息）。贷款人承诺按照监管要求对客户资料承担保密义务,除法律法规要求外，不得将收集到的用户相关信息提供给无关的第三方。 
</p><p>3.4 为了与本业务的合作第三方（包括公寓企业和蜂鸟屋平台）共同标识您的身份并为您提供相关服务，您授权贷款人向本业务的合作第三方（包括公寓企业和蜂鸟屋平台）提供您的个人信息（包括姓名、身份证号码及联络手机号等）。贷款人将督促本业务的合作第三方（包括公寓企业和蜂鸟屋平台）对您的个人信息严格保密，并不得向无关第三人披露上述资料。 
</p><p>3.5 贷款人有权依据您的资信自主决定是否接受您的借款申请及核定您的借款资格。</p>
<br><br><p class="subTitle">第四条、借款的使用</p> 
<p>4.1 在贷款人向您发放贷款前，您须向公寓企业支付首付款。若您获得借款资格后，未向公寓企业支付首付款，贷款人有权不向您提供借款服务。 
</p><p>4.2 贷款人向您发放的贷款，您不可撤销地授权贷款人以受托支付的方式一次性全额支付给公寓企业，用于您向公寓企业支付租金，您在任何情况下都不以现金形式提取贷款。 
</p><p>4.3 您知悉贷款人通过交易密码或手机短信验证码对使用本贷款的使用进行身份验证，并同意任何通过交易密码或手机短信验证码成功产生的交易均为其本人交易，并由您承担相应的交易后果。您应确保妥善保管并不向任何人泄露交易密码或手机短信验证码，对于因密码泄露所致的损失，由您自行承担。依据交易密码或手机短信验证码等电子数据信息办理的各类查询交易、结算交易、和还款交易均视为您本人所为，所产生的电子信息记录，均视为该项交易的有效凭证。 
</p><p>4.4 本合同项下单笔借款金额及其他相关信息以经您确认的电子借据所载信息为准。 
</p><p>4.5 若您在贷款期间出现监管机关规定的或贷款人依其主观判断认定的风险特征时，贷款人有权不经任何形式的事先通知或事先确认而随时中止或终止对您的贷款服务。</p> 
<br><br><p class="subTitle">第五条、还款 </p>
<p>5.1 若您的借款金额为您所租住房间 11 个月的租金，则借款本金分 11 期偿还；若您的借款金额为您所租住房间 5 个月的租金，则借款本金分 5 期偿还。<span style="text-decoration: underline ">您须在每月的还款日以足额支付账单规定金额的方式偿还贷款人。</span> 
</p><p>5.2 本合同项下的贷款利息由公寓企业承担并向贷款人支付。 
</p><p>5.3 还款顺序：贷款人扣收款项按照先违约金、手续费后本金的顺序按期还款。贷款人有权根据您的信用状况和贷款人的相关风险政策单方面变更前述还款顺序，而无需另行通知您。 
</p><p>5.4 还款账户变更：在您未清偿本合同项下所有借款违约金及本金前，您不得变更、注销您的还款账户。如遇特殊情况，经贷款人及第三方（蜂鸟屋平台）审批后您方可变更还款账户。 </p>
<br><br><p class="subTitle">第六条、合同变更、解除、权利义务的转让 </p>
<p>6.1 合同变更与解除 
</p><p>6.1.1 贷款人有权随时单方面修改本合同中与您相关的权利义务，<span style="text-decoration: underline ">但相关修改不得加重您在贷款金额和利（费）率方面的责任</span> 。一旦合同条款变更，贷款人将在线上渠道进行公示，除法律法规或监管规定另有强制性规定外，经修订的内容一经公示，立即生效。若您不同意修改本合同，则应当自该等告示之日起立即停止使用本服务并全额还清本合同项下的应付款项；否则，视为您同意并接受修改后的合同。 
</p><p>6.1.2 本合同生效后，除本合同另有约定外，您不得要求单方擅自变更或解除本合同。贷款人有权基于自身经营考虑，随时宣布中断、终止本合同或其任何部分，并要求您在指定期限内偿还本合同项下应付款项。 
</p><p>6.2 合同权利义务的转让：未经贷款人书面同意，您不得将本合同项下的权利和义务转让给任何第三方。贷款人有权将其在本合同项下的权利和义务全部或部分转让给第三方，且转让行为无须征得您的同意，贷款人将通知您该等转让行为。 </p>
<br><br><p class="subTitle">第七条、违约条款 </p>
<p>7.1 下列任一事件均构成本条款所称违约事件： 
</p><p>您未按双方约定的用途使用借款或将资金用于禁止领域； 
</p><p>您任何一期拖欠借款本金、违约金； 
</p><p>您在履行与贷款人或其他金融机构签订的其他合同时有违约行为； 
</p><p>您未履行本合同下任何义务的行为； 
</p><p>您向贷款人提供虚假的信息； 
</p><p>您是出于非真实的租住目的而向贷款人申请贷款； 
</p><p>您转移资产以逃避债务的； 
</p><p>您发生严重影响偿债能力的情形。 </p>

<p>7.2 有违约事件发生时，贷款人有权采取下列措施： 
</p><p>（1）要求您限期纠正违约行为； 
</p><p>（2）有权要求公寓企业将您清退出公寓； 
</p><p>要求您提前归还已发放的全部账单金额并结清违约金（如有）； 
</p><p>根据贷款风险状况调整贷款金额、期限与利率； 
</p><p>宣布本合同项下您未偿还的贷款提前到期，委托还款账户开户行或第三方支付机构组织从您的还款账户中扣收您应偿付的账单金额、违约金、以及所有其他应付费用，或以合法手段追偿您应付款项； 
</p><p>从您在贷款人任何营业机构开立的账户中扣收您应偿付的账单金额、违约金、复利以及所有其他应付费用； 
</p><p>对您的违约行为，可以公开披露； 
</p><p>采取法律、法规规定的其他救济措施。 
</p><p>7.3您任何一期未及时足额支付账单金额即视为逾期，并从逾期之日起按您所有应支付账单金额按天向您加收违约金。 
</p><p>7.4您任何一期未及时足额支付账单金额即视为逾期，从逾期之日起对逾期金额按日利率 0.1% 计收违约金，直至清偿逾期本息为止，贷款人有权按违约金利率计收复利。 
</p><p>7.5 若您主动与公寓企业提前解除租房合同，本合同项下的贷款，您应全部提前结清，您与公寓企业办理完毕退租操作之后，公寓企业将在租房合同解约日立即代您向贷款人支付本合同项下所有剩余账单金额、违约金及相关费用。 
</p><p>7.6 若公寓企业无法或承认无法向贷款人清偿本合同剩余账单金额、违约金和相关费用，贷款人仍有权利向您追偿相应款项，贷款人有权委托开户行或第三方支付机构组织从您还款账户或在贷款人任何营业机构开立的任何账户中扣收您应偿还的相应款项。 
</p><p>7.7 贷款人或/和第三方（蜂鸟屋）因向您催收欠款及实现债权而产生的一切费用（包括但不限于公证费、诉讼费、律师费、差旅费），均由您承担。 
</p><p>7.8 您同意贷款人有权在进行催收和追索债务等工作时，将您的身份信息、联络信息及您拖欠本合同项下债务的相关信息提供给第三方（包括律师事务所和催收机构）；且贷款人将督促该等第三方妥善保管、保密和谨慎使用前述信息，不得用作委托催收和追索债务以外的其他用途，以及不得以任何违法的方式进行催收和追索债务。 
</p><p>7.9 贷款人软（硬）件系统出现下列任一状况而无法正常运作，致使无法向您提供本服务，贷款人均不承担任何违约或赔偿责任，该状况包括但不限于： 
</p><p>（1） 在本服务线上渠道维护期间； 
</p><p>（2）通讯运营商设备出现故障不能进行数据传输的； 
</p><p>（3）因台风、地震、海啸、洪水、停电、战争、恐怖袭击等不可抗力之因素，造成本服务运行系统障碍不能执行业务的； 
</p><p>（4）由于黑客攻击、通讯运营商、还款账户开户行和其他第三方支付组织机构有信息技术依赖的相关部门、企事业单位技术调整或故障、网站升级等原因而造成的服务中断或者延迟。</p>
<br><br><p class="subTitle">第八条、附则 </p>
<p> 8.1 您应保证在安全环境下通过约定媒介使用借款，非安全环境下在互联网或其它媒介上使用借款所导致的风险和损失由您自行负责。 
</p><br><p>8.2 线上渠道所公布的服务收费标准、单笔借据及电子补充协议、附件是本协议不可分割的部分，与本协议具有同等法律效力。 
</p><br><p>8.3 您在向贷款人提供的资料及信息（包括但不限于姓名、国籍、住所地、工作单位、联系电话、身份证件或者身份证明文件的号码、有效期等身份信息）发生变更的，应在信息发生变更之日起 7 日内通过贷款人和第三方（蜂鸟屋平台）提供的线上渠道更新相关信息；贷款人就本协议给予其他方的任何通知、要求或其它函件，一经发送到您向贷款人提供的信息中所示的地址，即视为已送达，因您不及时变更信息而引起的责任及产生的损失，由您自行承担，贷款人有权因此停止为您发放新的贷款。 
</p><p>8.4 本合同及本合同项下电子补充协议、电子借款借据或附件（如有）已经经过第三方存证机构进行电子证据固化并保存，可以作为争议解决中的证据使用。 
</p><p>8.5 管辖及法律适用： 
</p><br><p>（1） 本合同签订地为中华人民共和国上海市全市范围。 
</p><br><p>（2） 本合同的成立、生效、履行、解释及纠纷解决，适用中华人民共和国大陆地区法律（不包括冲突法）。 
</p><br><p>（3） 若您和贷款人之间发生任何纠纷或争议，首先应友好协商解决；协商不成的，您同意将纠纷或争议提交本合同签订地有管辖权的人民法院管辖。 
</p><br><p>（4） 本合同条款无论因何种原因部分无效或不可执行，其余条款仍有效，对双方具有约束力。</p>

            </div>
    	</el-dialog>
    </div>
</template>
<script>
    export default {
        props: ['showDialog', 'currentContractInfo'],
        data: function() {
            return {
                isDlgVisable: this.showDialog,
                currentContract: this.currentContractInfo
            }
        },
        methods: {
            download() {
                kendo.drawing.drawDOM($('#personContract'), {
                    paperSize: "A4", margin: "10mm", scale: 0.50, template: '<div class="page-template"> \
                        <div class="header"> \
                            个人消费借款合同 \
                        </div> \
                        <div class="footer"> \
                            <span>#:pageNum# / #:totalPages#</span> \
                        </div> \
                    </div>',
                    keepTogether: ".prevent-split", forcePageBreak: ".page_break"
                }).then(function (group) {
                    var name = '个人消费借款合同';
                    kendo.drawing.pdf.saveAs(group, name + ".pdf");
                });
            }
        },
        watch: {
            showDialog(val) {
                this.isDlgVisable = val;
            },
            isDlgVisable(val) {
                this.$emit("on-result-change",val);
            }
        }
    }
</script>
<style scoped>
    #personContract {
        font-family: 'lanting', 'langtingxihei', 'sans-serif', 'Microsoft Himalaya'
    }
</style>
<style>
    .articleTitle {
        font-weight: 700;
        font-size: 24px;
        text-align: center
    }
    .subTitle {
        font-weight: 700;
        font-size: 16px;
    }
</style>