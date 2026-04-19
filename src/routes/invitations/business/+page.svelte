<script lang='ts'>
  import { Briefcase, ChartBar, Shield, Globe, Clock, Users, Award, ChevronRight, Zap } from '@lucide/svelte'

  const features = [
    { icon: Shield, title: 'Kurumsal Güvenlik', desc: 'KVKK uyumlu altyapı ile konuk bilgilerini güvenle saklayın.' },
    { icon: ChartBar, title: 'Detaylı Analitik', desc: 'Davetiye görüntülenme, tıklama ve katılım oranlarını raporlayın.' },
    { icon: Globe, title: 'Özel Alan Adı', desc: 'Şirketinizin domain\'i ile profesyonel bir davetiye yayınlayın.' },
    { icon: Clock, title: 'Etkinlik Programı', desc: 'Konuşmacılar, oturumlar ve molalar için detaylı program ekleyin.' },
    { icon: Users, title: 'Toplu Kayıt', desc: 'Yüzlerce katılımcıyı tek panelden yönetin ve CSV ile dışa aktarın.' },
    { icon: Award, title: 'Beyaz Etiket', desc: 'Platform logomuz olmadan tamamen kendi markanız gibi görünsün.' },
  ]

  const useCases = [
    { emoji: '🏢', title: 'Lansman Etkinliği', desc: 'Yeni ürün ve hizmetlerinizi tanıtın' },
    { emoji: '📊', title: 'Fuar & Konferans', desc: 'Sektörel etkinliklerde fark yaratın' },
    { emoji: '🤝', title: 'Networking', desc: 'İş bağlantılarınızı güçlendirin' },
    { emoji: '🎓', title: 'Seminer & Eğitim', desc: 'Kurumsal eğitim etkinliklerinizi planlayın' },
  ]
</script>

<svelte:head>
  <title>İş & Fuar Davetiyeleri — edavet.org</title>
  <meta name='description' content='Kurumsal etkinlikleriniz için prestijli ve profesyonel dijital davetiyeler. Analitik, KVKK uyumluluğu ve beyaz etiket desteği.' />
</svelte:head>

<!-- Hero - Premium Koyu Tema -->
<section class='relative min-h-[90vh] flex items-center overflow-hidden bg-[#0a0a0f]'>
  <!-- Premium Koyu Arka Plan -->
  <div class='absolute inset-0 z-0'>
    <div class='absolute top-[-10%] left-[-10%] w-[40%] h-[50%] bg-blue-600/10 rounded-full blur-[100px]'></div>
    <div class='absolute bottom-[-10%] right-[-10%] w-[40%] h-[50%] bg-violet-600/10 rounded-full blur-[100px]'></div>
    <div class='absolute top-[30%] right-[30%] w-[15%] h-[15%] bg-cyan-500/5 rounded-full blur-[80px]'></div>
  </div>
  <!-- Grid Overlay -->
  <div class='absolute inset-0 z-0 opacity-[0.03]' style='background-image: linear-gradient(rgba(255,255,255,.1) 1px, transparent 1px), linear-gradient(90deg, rgba(255,255,255,.1) 1px, transparent 1px); background-size: 60px 60px;'></div>

  <div class='container mx-auto px-4 relative z-10 py-20'>
    <div class='flex flex-col lg:flex-row items-center gap-12 lg:gap-20'>
      
      <!-- Text Content -->
      <div class='flex-1 text-center lg:text-left'>
        <div class='inline-flex items-center gap-2 bg-blue-500/10 border border-blue-500/20 text-blue-400 rounded-full py-2 px-6 mb-8 text-sm font-bold uppercase tracking-widest backdrop-blur-md'>
          <Briefcase class='w-4 h-4' />
          Kurumsal Prestij & İmaj
        </div>

        <h1 class='text-4xl md:text-6xl font-black mb-6 tracking-tight leading-[1.1] text-white'>
          İş Etkinliklerinize <br />
          <span class='bg-gradient-to-r from-blue-400 via-cyan-300 to-violet-400 bg-clip-text text-transparent italic font-serif'>Dijital Vizyon Katın.</span>
        </h1>

        <p class='text-lg md:text-xl text-gray-400 mb-10 font-medium leading-relaxed max-w-xl mx-auto lg:mx-0'>
          Lansman, fuar ve konferanslarınız için profesyonel dijital davetiyeler. Detaylı analitik, toplu kayıt yönetimi ve beyaz etiket desteğiyle <span class="text-blue-400 font-bold">marka imajınızı güçlendirin.</span>
        </p>

        <div class='flex flex-col sm:flex-row gap-4 justify-center lg:justify-start'>
          <a href='/invitations/custom' class='btn btn-lg bg-blue-600 hover:bg-blue-500 border-0 text-white shadow-xl shadow-blue-500/20 hover:-translate-y-1 transition-all rounded-[14px] px-10'>
            Hemen Tasarla
          </a>
          <a href='/contact' class='btn btn-lg bg-white/5 border border-white/10 text-white/70 hover:bg-white/10 px-10 rounded-[14px]'>
            Profesyonel Destek
          </a>
        </div>

        <!-- Trust Badges -->
        <div class='mt-12 flex flex-wrap justify-center lg:justify-start gap-6 text-gray-500/60 items-center'>
          <span class='text-xs font-bold uppercase tracking-widest border border-white/5 px-3 py-1 rounded'>Fortune 500</span>
          <span class='text-xs font-bold uppercase tracking-widest border border-white/5 px-3 py-1 rounded'>ISO 27001</span>
          <span class='text-xs font-bold uppercase tracking-widest border border-white/5 px-3 py-1 rounded'>KVKK Uyumlu</span>
        </div>
      </div>

      <!-- Hero Visual (Business Preview) -->
      <div class='flex-1 flex justify-center lg:justify-end w-full'>
        <div class="relative w-full max-w-md">
           <!-- Data Tags -->
           <div class='absolute -top-6 -right-6 bg-blue-600 text-white rounded-2xl p-4 shadow-2xl z-20 animate-pulse border border-white/20 hidden sm:block'>
              <div class="flex items-center gap-2">
                <ChartBar class="w-5 h-5" />
                <span class="font-bold text-sm">Aktif Takip</span>
              </div>
           </div>

          <!-- Phone Mockup Shadow -->
          <div class="absolute -inset-10 bg-blue-500/10 rounded-full blur-[100px]"></div>
          
          <div class="relative rounded-[36px] border-[8px] border-white/5 shadow-2xl overflow-hidden aspect-[9/16] bg-slate-900 border-base-200">
             <div class="absolute inset-0 bg-gradient-to-br from-slate-900 to-black"></div>
             <!-- Mockup Content -->
             <div class="absolute inset-0 p-8 flex flex-col justify-center items-center text-center">
                <div class="w-16 h-16 bg-blue-500/20 rounded-2xl flex items-center justify-center mb-6 border border-blue-500/30">
                  <Briefcase class="w-8 h-8 text-blue-400" />
                </div>
                <h3 class="text-2xl font-bold text-white mb-4">Tech Summit 2026</h3>
                <div class="h-px w-full bg-white/10 mb-6"></div>
                <div class="space-y-3 w-full">
                  <div class="h-2 bg-white/5 rounded-full w-3/4 mx-auto"></div>
                  <div class="h-2 bg-white/5 rounded-full w-1/2 mx-auto"></div>
                  <div class="h-2 bg-white/5 rounded-full w-2/3 mx-auto"></div>
                </div>
                <div class="mt-8 px-6 py-2 bg-blue-600 rounded-lg text-xs font-bold text-white">KATILIM ONAYLA</div>
             </div>
          </div>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- Önizleme Kartı -->
<section class='py-24 bg-[#0d0d14] relative overflow-hidden'>
  <div class='absolute inset-0'>
    <div class='absolute top-[20%] right-[5%] w-[15%] h-[15%] bg-blue-600/5 rounded-full blur-[80px]'></div>
  </div>
  <div class='container mx-auto px-4 relative z-10'>
    <div class='text-center mb-16'>
      <h2 class='text-4xl md:text-5xl font-black mb-4 tracking-tight text-white'>
        Profesyonel <span class='text-blue-400'>Görünüm</span>
      </h2>
      <p class='text-gray-400 text-lg max-w-xl mx-auto font-medium'>Kurumsal kimliğinizle uyumlu şık davetiyeler.</p>
    </div>
    <div class='max-w-lg mx-auto'>
      <div class='card bg-gradient-to-b from-gray-900 to-gray-950 shadow-2xl border border-white/10 overflow-hidden'>
        <div class='h-1 bg-gradient-to-r from-blue-500 via-cyan-500 to-violet-500'></div>
        <div class='card-body items-center text-center p-10'>
          <div class='w-16 h-16 bg-blue-500/10 rounded-2xl flex items-center justify-center mb-4'>
            <Briefcase class='w-8 h-8 text-blue-400' />
          </div>
          <p class='text-blue-400 font-semibold tracking-widest text-xs uppercase'>Davetlisiniz</p>
          <h3 class='text-3xl font-black text-white mt-2'>Tech Summit 2026</h3>
          <p class='text-gray-400 font-medium mt-2'>Geleceğin Teknolojileri Konferansı</p>
          <div class='divider before:bg-white/10 after:bg-white/10 my-4'></div>
          <div class='grid grid-cols-3 gap-4 w-full text-center'>
            <div>
              <div class='text-xs text-gray-500 uppercase tracking-wider font-medium'>Tarih</div>
              <div class='text-white font-bold text-sm'>10 Ekim 2026</div>
            </div>
            <div>
              <div class='text-xs text-gray-500 uppercase tracking-wider font-medium'>Saat</div>
              <div class='text-white font-bold text-sm'>09:00 - 18:00</div>
            </div>
            <div>
              <div class='text-xs text-gray-500 uppercase tracking-wider font-medium'>Mekan</div>
              <div class='text-white font-bold text-sm'>Hilton İstanbul</div>
            </div>
          </div>
          <div class='flex gap-3 mt-8'>
            <button class='btn btn-sm bg-blue-500 border-0 text-white hover:bg-blue-600'>Kayıt Ol</button>
            <button class='btn btn-sm bg-white/5 border border-white/10 text-white hover:bg-white/10'>Program</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- Kullanım Alanları -->
<section class='py-24 bg-[#0a0a0f]'>
  <div class='container mx-auto px-4'>
    <div class='text-center mb-16'>
      <h2 class='text-4xl md:text-5xl font-black mb-4 tracking-tight text-white'>Her <span class='text-blue-400'>Etkinliğe</span> Uygun</h2>
    </div>
    <div class='grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6 max-w-5xl mx-auto'>
      {#each useCases as uc}
        <div class='card bg-white/[0.03] border border-white/10 hover:border-blue-500/30 transition-all group hover:-translate-y-2 cursor-pointer'>
          <div class='card-body items-center text-center p-8'>
            <div class='text-5xl mb-4 group-hover:scale-125 transition-transform'>{uc.emoji}</div>
            <h3 class='font-bold text-white text-lg'>{uc.title}</h3>
            <p class='text-gray-500 text-sm font-medium'>{uc.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- Özellikler -->
<section class='py-24 bg-[#0d0d14]'>
  <div class='container mx-auto px-4'>
    <div class='text-center mb-16'>
      <h2 class='text-4xl md:text-5xl font-black mb-4 tracking-tight text-white'>Kurumsal <span class='text-blue-400'>Özellikler</span></h2>
      <p class='text-gray-400 text-lg max-w-xl mx-auto font-medium'>İşletmenizin ihtiyaç duyduğu her şey.</p>
    </div>
    <div class='grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-5xl mx-auto'>
      {#each features as f}
        <div class='card bg-white/[0.03] border border-white/10 hover:border-blue-500/20 transition-all group hover:-translate-y-2'>
          <div class='card-body p-8'>
            <div class='w-14 h-14 bg-blue-500/10 rounded-2xl flex items-center justify-center mb-4 text-blue-400 group-hover:scale-110 group-hover:bg-blue-500 group-hover:text-white transition-all duration-300'>
              <f.icon class='w-7 h-7' />
            </div>
            <h3 class='text-xl font-bold mb-2 text-white'>{f.title}</h3>
            <p class='text-gray-400 font-medium leading-relaxed'>{f.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>

<!-- CTA -->
<section class='py-24 bg-gradient-to-r from-blue-600 via-blue-500 to-violet-600 text-white relative overflow-hidden'>
  <div class='absolute inset-0'>
    <div class='absolute top-[-20%] left-[10%] w-[30%] h-[60%] bg-white/5 rounded-full blur-3xl'></div>
    <div class='absolute bottom-[-20%] right-[10%] w-[30%] h-[60%] bg-white/5 rounded-full blur-3xl'></div>
  </div>
  <div class='container mx-auto px-4 relative z-10 text-center'>
    <div class='w-16 h-16 bg-white/10 rounded-2xl flex items-center justify-center mx-auto mb-6'>
      <Briefcase class='w-8 h-8' />
    </div>
    <h2 class='text-4xl md:text-5xl font-black mb-4'>İşinizi Büyütmeye Hazır Mısınız?</h2>
    <p class='text-white/80 text-lg max-w-xl mx-auto mb-8 font-medium'>Kurumsal etkinlikleriniz için özel teklif alın.</p>
    <a href='/contact' class='btn btn-lg bg-white text-blue-600 border-0 shadow-xl hover:scale-105 transition-all font-bold px-10'>
      Teklif İste
      <ChevronRight class='w-5 h-5' />
    </a>
  </div>
</section>
