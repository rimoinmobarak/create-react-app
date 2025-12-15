import React from 'react';
import { MapPin, Star, Users, Gift, Clock, Phone, MessageCircle, CheckCircle } from 'lucide-react';

// --- Main App Component ---
const App = () => {
  const phoneNumber = "01737177017"; 
  const displayNumber = "01737-177017";

  const handleWhatsApp = () => {
    // Open WhatsApp with the number
    window.open(`https://wa.me/88${phoneNumber}`, '_blank');
  };

  return (
    <div className="min-h-screen bg-slate-100 flex items-center justify-center p-4 font-sans">
      
      {/* Main Poster Card (Mobile-Friendly Layout) */}
      <div className="w-full max-w-md bg-white rounded-3xl shadow-2xl overflow-hidden transform transition-all duration-300 hover:shadow-3xl border border-slate-200">
        
        {/* Header Section */}
        <div className="bg-white pt-10 pb-6 px-8 text-center relative border-b border-slate-100 flex flex-col items-center">
          
          <div className="inline-flex items-center gap-1 bg-[#78a33d] text-white text-xs font-bold px-3 py-1 rounded-full mb-6 shadow-sm">
            <MapPin size={12} />
            রাজশাহী ভিজিট
          </div>
          
          {/* Logo Construction */}
          <div className="relative mb-2">
            <h1 className="text-6xl font-extrabold tracking-tight leading-none">
              <span className="text-[#78a33d]">RI</span>
              <span className="text-[#383e42]">MO</span>
            </h1>
          </div>
          
          <p className="text-gray-400 text-[13px] font-bold tracking-[0.2em] mt-2 uppercase">Interior & Architecture</p>
        </div>

        {/* Body Content */}
        <div className="p-6 space-y-6 bg-white">

          {/* Alert Box - Main Event Highlight */}
          <div className={`border-l-4 p-4 rounded-r-lg bg-[#f4f9ef] border-[#78a33d]`}>
            <h3 className={`font-bold text-lg flex items-center gap-2 text-[#4a6327]`}>
              <Clock size={20} />
              রাজশাহী ভিজিট ও কনসালটেশন 🎯
            </h3>
            <p className="text-slate-600 text-sm mt-1 font-medium">
              আপনার ফ্ল্যাট বা বাড়ির জন্য Interior ডিজাইন নিয়ে সরাসরি Rimo টিমের সাথে আলোচনার সুযোগ।
            </p>
          </div>

          {/* Core Message */}
          <div className="text-center bg-gray-50 p-4 rounded-lg border border-gray-200">
            <p className="text-xl font-bold text-[#383e42]">
              আমাদের পরবর্তী ভিজিট স্লট বুক করুন!
            </p>
            <p className="text-sm text-gray-500 mt-1">
              দ্রুত মিটিং নিশ্চিত করতে WhatsApp-এ যোগাযোগ করুন।
            </p>
          </div>

          {/* Features Grid */}
          <div className="grid grid-cols-2 gap-3">
            <FeatureCard icon={<Star size={18} />} title="কাস্টম ডিজাইন" color="bg-slate-700" />
            <FeatureCard icon={<CheckCircle size={18} />} title="প্রিমিয়াম ফিনিশিং" color="bg-[#78a33d]" />
            <FeatureCard icon={<Users size={18} />} title="এক্সপার্ট টিম" color="bg-slate-700" />
            <FeatureCard icon={<Gift size={18} />} title="ফ্রি কনসালটেশন" color="bg-[#78a33d]" />
          </div>

          {/* Call to Action - WhatsApp Button */}
          <div className="bg-[#383e42] rounded-xl p-6 text-center text-white relative overflow-hidden group">
            {/* Background decoration */}
            <div className="absolute top-0 right-0 w-32 h-32 bg-[#78a33d] rounded-full blur-3xl opacity-20 -mr-16 -mt-16"></div>
            
            <div className="relative z-10">
              <p className="text-gray-300 text-sm mb-3 font-medium uppercase tracking-wide">সরাসরি কথা বলতে ক্লিক করুন</p>
              
              <button 
                onClick={handleWhatsApp}
                className="w-full bg-[#78a33d] text-white font-bold py-3 px-4 rounded-lg flex items-center justify-center gap-2 hover:bg-[#668c33] transition-colors shadow-lg active:scale-95"
              >
                <MessageCircle size={24} />
                <span className="text-xl tracking-wide">WhatsApp করুন</span>
              </button>
              
              <div className="mt-4 flex items-center justify-center gap-2 text-gray-400 text-sm">
                <Phone size={14} />
                <span>কল করুন: {displayNumber}</span>
              </div>
            </div>
          </div>

        </div>

        {/* Footer */}
        <div className="bg-slate-50 p-4 text-center border-t border-slate-100">
          <p className="font-bold text-slate-700 tracking-wider text-xs">RIMO INTERIOR & ARCHITECTURE</p>
          <p className="text-[10px] text-slate-400 mt-1">Design with Confidence | আপনার বিশ্বাস, আমাদের দায়িত্ব 🏡</p>
        </div>

      </div>
    </div>
  );
};

// Helper Component for Features
const FeatureCard = ({ icon, title, color }) => (
  <div className="flex flex-col items-center justify-center p-3 rounded-xl bg-slate-50 hover:bg-white hover:shadow-md transition-all border border-slate-100 group cursor-default">
    <div className={`${color} text-white p-2.5 rounded-full mb-2 shadow-sm group-hover:scale-110 transition-transform`}>
      {icon}
    </div>
    <span className="text-slate-600 font-semibold text-sm">{title}</span>
  </div>
);

export default App;
